# JAVA API特别提示

## java.io
### java.io.Reader
#### java.io.BufferedReader
> :turtle: Without buffering, each invocation of read() or readLine() could cause bytes to be read from the file, converted into characters, and then returned, which can be very inefficient.

> :thought_balloon: Programs that use DataInputStreams for textual input can be localized by replacing each DataInputStream with an appropriate BufferedReader.
