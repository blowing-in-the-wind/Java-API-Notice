# JAVA API特别提示

## java.io
### java.io.Reader
#### java.io.BufferedReader
> :turtle: In general, each read request made of a Reader causes a corresponding read request to be made of the underlying character or byte stream. It is therefore advisable to wrap a BufferedReader around any Reader whose read() operations may be costly, such as FileReaders and InputStreamReaders. For example,
>> `BufferedReader in = new BufferedReader(new FileReader("foo.in"));`
> 
> will buffer the input from the specified file. Without buffering, each invocation of read() or readLine() could cause bytes to be read from the file, converted into characters, and then returned, which can be very inefficient.

> :thought_balloon: Programs that use DataInputStreams for textual input can be localized by replacing each DataInputStream with an appropriate BufferedReader.
