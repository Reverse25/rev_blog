This challenge does not provide any clue and assume that we know what we are doing. Okay let's open Begin Hack.jpgthe newly downloaded file

eog Begin \ Hack.jpg
Begin Hack

After opening with the image viewer there is no meaningful information and only ordinary images.

we do the string operation on the file

strings Begin \ Hack.jpg | more
Notice a few words that can be read when we scroll . There is one URL, open that URL and download the file there.

https://mega.nz/#!z8hACJbb!vQB569ptyQjNEoxIwHrUhwWu5WCj1JWmU-OFjf90Prg

Extract the file

unzip Up \ For \ A \ Little \ Challenge.zip
After extracting we get 2 folders namely Did I Forget Again?and __MACOSX. The folder that we will browse is Did I Forget Again?, while the folder __MACOSXis a folder that is automatically created when creating archives using a Mac computer. ( Read here )

cd Did\ I\ Forget\ Again\?
ls -la
Here there are 1 image file and 1 hidden file with the extension cerb4. If we open the file Loo Nothing Becomes Useless ack.jpgthere will be no information provided, as well as when we see the string from this image.

eog Loo\ Nothing\ Becomes\ Useless\ ack.jpg
strings eog Loo\ Nothing\ Becomes\ Useless\ ack.jpg
This time we try to examine what is the .Processing.cerb4 file

file .Processing.cerb4
Once seen, it turns out that this file type is Zip . therefore we need to change / add extensions .zipbehind file names. Then do the extracting .

mv .Processing.cerb4 .Processing.cerb4.zip
unzip .Processing.cerb4.zip
When trying to extract this file, we are asked to enter a password. Then where can we get the password?

Okay, now we go back to the first file and see that there is a password that can be used to extract the file.

cd ..
strings Begin\ Hack.jpg | more
Nothing Is As It Seems

Then we extract the file .Processing.cerb4.zipwith the password that we got. Finally, we open the extracted file .

cd Did\ I\ Forget\ Again\?
unzip .Processing.cerb4.zip
eog skycoder.jpg
the flag is in the image.just zoom in.

flag: flag{hack_complete}
