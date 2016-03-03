//static_cast用來做型態轉換
static_cast<int>(numRows -1);

//int2 2d dim
//const int2 thread_2D_pos = make_int2(threadX, threadY);

const int2 thread_2D_pos = make_int2( blockIdx.x * blockDim.x + threadIdx.x,
                                        blockIdx.y * blockDim.y + threadIdx.y);
//轉1D call x 或 y
const int thread_1D_pos = thread_2D_pos.y * numCols + thread_2D_pos.x;

//min,max 在gpu 裡面不用加上std
