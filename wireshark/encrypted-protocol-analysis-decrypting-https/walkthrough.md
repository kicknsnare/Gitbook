# Walkthrough

\
Use the "Desktop/exercise-pcaps/https/Exercise.pcap" file.\
What is the frame number of the "Client Hello" message sent to "accounts.google.com"?

&#x20;<mark style="color:green;">16</mark>

<figure><img src="https://camo.githubusercontent.com/61346d58bb9b8cb47c7ed075cfb2a815f8e0f8ef899bb6c944b98670309185d7/68747470733a2f2f692e696d6775722e636f6d2f4732684b766a482e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/a8847277e106ffd0ebc3ed3bd5242b261fa7b6c8facba1a92c1080d3003b866a/68747470733a2f2f692e696d6775722e636f6d2f556551315743672e706e67" alt=""><figcaption></figcaption></figure>

Decrypt the traffic with the "KeysLogFile.txt" file. What is the number of HTTP2 packets?

<mark style="color:green;">115</mark>

<figure><img src="https://camo.githubusercontent.com/58c55f60866ee375b825c3897ed69f4444a9f0af4cc8aaaa141968f72ffbf0a1/68747470733a2f2f692e696d6775722e636f6d2f677239465165672e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/f4d933eba21ca640790d248b2ef8dff4baf28baa3d94ebbfa002976a59a5baec/68747470733a2f2f692e696d6775722e636f6d2f464b41584844362e706e67" alt=""><figcaption></figcaption></figure>

Go to Frame 322. What is the authority header of the HTTP2 packet? (Enter the address in defanged format.)

&#x20;<mark style="color:green;">safebrowsing\[.]googleapis\[.]com</mark>

<figure><img src="https://camo.githubusercontent.com/e28c75fc405571d3cb1502eeed996c8414b229751c3a520a6591355b62a981f0/68747470733a2f2f692e696d6775722e636f6d2f327345623165342e706e67" alt=""><figcaption></figcaption></figure>



Investigate the decrypted packets and find the flag! What is the flag?

&#x20;<mark style="color:green;">FLAG{THM-PACKETMASTER}</mark>\


<figure><img src="https://camo.githubusercontent.com/c7f4e633ecdc10384057302bdce7f340057d62f230c2207d2b6c34ad1664a51a/68747470733a2f2f692e696d6775722e636f6d2f78426335364c552e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/a215d6b585afae9a1753206192227cbcf66e4ddbe0200e6d400815d5bb7a093b/68747470733a2f2f692e696d6775722e636f6d2f536d3264426b732e706e67" alt=""><figcaption></figcaption></figure>
