# JAVA API特别提示

## java.io
### java.io.BufferedReader
> :turtle: In general, each read request made of a Reader causes a corresponding read request to be made of the underlying character or byte stream. It is therefore advisable to wrap a BufferedReader around any Reader whose read() operations may be costly, such as FileReaders and InputStreamReaders. For example,
>> `BufferedReader in = new BufferedReader(new FileReader("foo.in"));`
> 
> will buffer the input from the specified file. Without buffering, each invocation of read() or readLine() could cause bytes to be read from the file, converted into characters, and then returned, which can be very inefficient.

> :thought_balloon: Programs that use DataInputStreams for textual input can be localized by replacing each DataInputStream with an appropriate BufferedReader.

## java.nio
### java.nio.channels.FileChannel
> :turtle: A region of a file may be [mapped](https://docs.oracle.com/javase/8/docs/api/java/nio/channels/FileChannel.html#map-java.nio.channels.FileChannel.MapMode-long-long-) directly into memory; for large files this is often much more efficient than invoking the usual read or write methods.
>
> :turtle: Bytes can be transferred from a file [to some other channel](https://docs.oracle.com/javase/8/docs/api/java/nio/channels/FileChannel.html#transferTo-long-long-java.nio.channels.WritableByteChannel-), and [vice versa](https://docs.oracle.com/javase/8/docs/api/java/nio/channels/FileChannel.html#transferFrom-java.nio.channels.ReadableByteChannel-long-long-), in a way that can be optimized by many operating systems into a very fast transfer directly to or from the filesystem cache.
