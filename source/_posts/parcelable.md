Parcelable

序列化:将对象装华为可以传输的二进制流（二进制序列的过程）

Parcel：提供了一套机制，可以将序列化之后的数据写入到一个共享内存中，其他进程通过Parcel可以从这块共享内存中读出字节（Binder 机制），并反序列化成对象,下图是这个过程的模型。。