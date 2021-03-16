# 1) Trials on Local Machine
**k=2**  
	*xS*=1875416056this_is_a_bitcoin_block_of_67460444  
	*hash*=00cd7780a82697ec5cc2ceabd34af4844ba9b83fce8a78c9137b0d1ed66061a1  
        *trials*=300  
	*Time elapsed*=6s  
**k=3**  
	*xS*=2013635984this_is_a_bitcoin_block_of_67460444  
	*hash*=000d7432ea4505de7adc7185eb42518817d12b59426936611668b091637f7e70  
        *trials*=5,000  
	*Time elapsed*=3s  
**k=4**  
	*xS*=1617404475this_is_a_bitcoin_block_of_67460444  
	*hash*=0000d2e2762b521d356b0b93f559c302ec510bc39829276eb9ee6d24d553e8fc  
        *trials*=75,000  
	*Time elapsed*=3s  
**k=5**  
	*xS*=894799934this_is_a_bitcoin_block_of_67460444  
	*hash*=00000f1a7324817e2fd1993042bfbf91da8e134277efc6707d0c92a3a8331336  
        *trials*=1,200,000  
	*Time elapsed*=4s  
**k=6**  
	*xS*=511950491this_is_a_bitcoin_block_of_67460444  
	*hash*=0000003f868c836049eefce2a4deaca3c62cbd4133ed965312be11df6c721832  
        *trials*=17,000,000  
	*Time elapsed*=16s  

# 2) Trials on GCP
**k=7**  
	*xS*=1150962390this_is_a_bitcoin_block_of_67460444  
	*hash*=000000078f1b557c2942b1a81ac7df02d90cc0e1c816a532c3cbe86e617e2b63  
        *trials*=285,000,000  
	*Time elapsed*=1083s  

I used the default cluster settings because I figured it wouldn't make a huge difference in runtime. 
This means 1 Master Node with 4 cores and 2 Worker Nodes with 4 cores, each with 15GB of memory. To find the number of trials, I first found 16^7, 
since there are 16 equally likely options for each character in the hash. I then added 20,000,000 extra trials because some random numbers will be generated more than once.

# 3) Changing from randomness to iteration
Iteration is more efficient than the randomized approach for large **k** because there is no chance for redundancy (Hashing a string that has already been checked).