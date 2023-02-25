JAVA I/O
<hr>
- Java Input and Output (I/O) is used to process the input and produce an output.

- All fundamental I/O in Java is based on streams.

- A stream represents a flow of data, or a channel of communication.
  - A stream is a sequence of data. 
  - In java, a stream is composed of bytes (units of memory).

- Different types of streams are provided by Java
  - InputStream/OutputStream
  - InputStreamReader/OutputStreamWriter
  - DataInputStream/DataOutputStream
  - ObjectInputStream/ObjectOutputStream
  - FileInputStream/FileOutputStream
 
- You use a stream of one type or another while working with
  - Terminal input and output
  - Reading or writing files
  - Communicating through sockets in java

- InputStream/OutputStream
 - Java applications use an input stream to read data from a source (it can be a file, peripheral device, or a socket).
 - Java applications use an output stream to write data to a destination (it can be a file, peripheral device, or a socket).
<img width="475" alt="image" src="https://user-images.githubusercontent.com/88880169/221373382-f4c3862a-7aca-44ac-977a-21870d66a332.png">
 <img width="582" alt="image" src="https://user-images.githubusercontent.com/88880169/221373423-cf4c4916-4db5-47c2-8495-2f78fc31bfa1.png">

- Byte Streams
  - All byte stream classes are descended from InputStream and OutputStream.
<img width="468" alt="image" src="https://user-images.githubusercontent.com/88880169/221373492-671a6248-fff4-4b4d-b344-fa6e4e305256.png">

- Character Streams
  - The character stream classes Reader and Writer were introduced in Java 1.1.Reader and Writer are abstract classes for reading and writing character streams.

<img width="510" alt="image" src="https://user-images.githubusercontent.com/88880169/221373873-640bfe99-e91e-458a-bbbb-123c742685c0.png">



