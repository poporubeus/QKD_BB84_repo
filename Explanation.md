# Circuit embedding
....

# Graph results
### Brief discussion on graphs I got

On the x axis you can see "probability to make an error" and is in fact the probability with which the noise model with the bit flip occurs.
On the y axis there's the quantity that Bob has been read correctly, i.e. the learnt message.
The multiple lines represent each of the 10 messages of length 1 to 10 encoded into multiple qubits used to evaluate the noise effect.
Note that the quantity that Bob manages to read corresponds to the used number of counts/shots: that is how many times Alice resends the message to Bob in order
to allow him to recognize as many bits as possible.
The idea is that even though Alice sends a message long 100 bits but only one time, Bob gets only 50 bits since he rolls at random. This is due to the fact that Alice has sent the message just once! In this way, even the circuit was noiseless, Bob wouldn't have been able to understand the message completely. This is the algorithm efficiency!
You can understand that reducing the message length is not necessarily connects to the quantity of message Bob decipheres. By increasing (not presented here) the number of counts we'd see that, without any source of error (realized by the condition of zero probability of making bit flip), the message would've been understood at 100%.
Now, with the introduction of a noise source within the circuit, the entire quantity of readable message should decrease as error probability increases even with many or few counts.
The exact message Bob can understand (without error) does not depend linearly to the number of counts: for the first count Bob gets half of the message, but for the second sending he gets again only 50% of the message and it's really improbable that he can get exactly the other half, but it's more favorable to get new bits and the old ones.
The standard deviation you can see for each line has been diminished by a factor comparable to the length of the mean_list. This has been done in order to make the visualization more easy for users, otherwise you'd have found a larger standard deviation for shorter messages. The fact is due to statistics. If I have a short message then I have a big instability. For those messages I can observe scenarios where Bob decipheres it totally or he decipheres nothing (1 bit), but increasing this number Bob has many other possibilities to detect different fractions of longer bit strings. 
