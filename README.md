# a silly lil writeup of hts realistic 10  
So, this is actually my first time doing this lol. I only realized at the very end of making this writeup (I thought I just forgot)

The lil blurb from our best buddy Zach Sanchez who foolishly gives a hacker his username and password
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/ccbf04e3-8ab4-40cb-b0cb-574b5249a4dd)

This is the main page
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/8ec06f76-1023-48e2-b76d-599dfe0bc726)  
Where there are 2 other pages:  
Staff listing  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/76e6dc04-6a4a-4afd-87ce-332a8e1d43e4)  
And a student login page  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/d550501f-c301-4772-9a41-18d0b1826ab7)  
The staff listing page has small informational pages about each teacher too  
Like Mr. Matthew Howard's page  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/32eb3e29-9b0c-48fe-a28c-49543be42bdd)  
Or my long lost cousin :O  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/d0a1b219-bd7a-4d32-b588-dc1a9ff88bb6)  
Fun little thing  
I did notice that each teacher had an ID number.
There were numbers for all 21 teachers.
On the list, they were organized by the first letter of their names on the page so I figured the ID number was the order they had their page up.  
ID=1 was probably the one who made the site. Mrs. Samantha Miller.  
Getting ahead of myself again  
Now we login as Zach  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/1626b534-ccd6-4b70-b228-6d303fca0f60)  
Now we have his address (this whole thing was not very smart on Zach's part)  
If you click on the subjects, you can see his grades  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/8056a6fd-a5f3-47bc-b694-298fb5ae1592)  
We gotta find the page that'll give us access to the grades  
So I'm just takin a look at the main page's source  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/dcd253ac-ba8d-4b63-8eae-e1dcda528c9c)  
There's a silly little staff.php that we can fuck with  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/59a05678-49f8-423d-acdc-beff6256a0df)  
But it's password protected :(  
So I played around with a bunch of stuff here.  
I tried sql injections and whatnot but it wasn't workin.  
So I bruteforced it.  
We know Mrs. Samantha Miller maybe perschance made the site. Irl I would probably look around her social media and whatnot to try to find possible passwords. But, she's fake so I had to go with what I knew.
All that time was wasted though, bc it was just her username :P
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/3e0d6075-22a5-4312-b62a-9cd71d1cbb5e)  
This is pretty simple to get past, just spoof the site with a lovely lil user agent switcher.  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/23cd536c-2152-4574-8779-f3cc0e8f95e9)  
Now we have staff access, but we are not administrator, so no grade changes :(  
Had to look around smore and I found smth interesting in my cookies.  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/7543d350-31df-419c-8433-27df04b19e98)  
This probably means my admin is off bc zero is nothing. So I made it one.
Now the thing telling me to bake off ( :P ) is gone  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/e049ee2b-61cc-4e01-88fb-591d90a14ea2)  
When you click change grades, you see all the students:  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/ff2aaee9-d8d6-47d0-9f3f-78d86c401d27)  
If you click on Zach, you can see all of his grades  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/c07c1cd4-4b01-40e1-be56-c944277b8ed6)  
Unfortunately, we are still monumentally fucked bc the due dates have passed.  
Normally I would use Burp here, but I don't have any of the extensions I installed on chromium and Burp don't work with edge :<  
So I will do everything in the search bar.  
Lookin at the page source, you can see an action  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/d3eec27f-52b8-430e-b109-19587c0bf910)  
So I'm just gonna schloink that, and stick it in the search bar  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/bda9526b-2966-4d26-9c9c-096f19b257f1)  
I still have to change the grade though, so I gotta stick &grade=5  
It goes from this:  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/e3a9fb3c-4f88-4d02-b2c4-55ad5782a104)  
To this:  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/8b72f05e-4736-4f5e-9a2a-bb4a425a0126)  
Now my first though, is to get silly with it and add a &comments=smth silly to the end  
So I did that with the second one  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/56381192-a092-4ba7-80fb-c4a75f119f73)  
Then I just finished quickly (rarely happens, I promise)  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/1b55cf40-f104-4838-b80e-f14c6909c57f)  
![image](https://github.com/saltytine/hts-realistic-10/assets/156854448/0cfd7ae7-62ba-4c10-8b56-0bf73fa64f7f)
