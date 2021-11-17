# Encrypting and Decrypting Basic plain text data

``` shell
ska@ska-ubuntu-vb:~/openssl_stuff$ echo "Hell world" > plain.txt
ska@ska-ubuntu-vb:~/openssl_stuff$ ls
plain.txt
ska@ska-ubuntu-vb:~/openssl_stuff$ cat plain.txt 
Hell world
ska@ska-ubuntu-vb:~/openssl_stuff$ openssl enc -aes-256-cbc -in plain.txt -out encrypted.bin
enter aes-256-cbc encryption password:
Verifying - enter aes-256-cbc encryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
ska@ska-ubuntu-vb:~/openssl_stuff$ ls
encrypted.bin  plain.txt
ska@ska-ubuntu-vb:~/openssl_stuff$ cat encrypted.bin 
Salted__�)CY� �8
                땠��*���'��ska@ska-ubuntu-vb:~/openssl_stuff$ 
ska@ska-ubuntu-vb:~/openssl_stuff$ 
ska@ska-ubuntu-vb:~/openssl_stuff$ openssl enc -aes-256-cbc -d -in encrypted.bin -pass pass:password
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
Hell world
ska@ska-ubuntu-vb:~/openssl_stuff$ ls
encrypted.bin  plain.txt
ska@ska-ubuntu-vb:~/openssl_stuff$ 


```

