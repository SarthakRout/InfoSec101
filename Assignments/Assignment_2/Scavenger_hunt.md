
 Author:[Raghavendra](https://github.com/Raghavendra1933)
Challenge Page:Scavenger Hunt(http://mercury.picoctf.net:5080/)
 Walkthrough:when we open the above link, we get how,what columns, on the what column we can see HTML,CSS,Js are used to make these website. Now click ctrl-U and ull land on a page, where u can find first part of flag(picoCTF{t),and 2 files. First one is CSS, by opening it well find second part of flag(h4ts_4_l0).Second file id Js, opening it ull find a page,where u see /*how can I keep Google from indexing my website*/, which can be done only by changind myjs.js in page link to robots.txt,then ull find 3rd part(t_0f_pl4c). and in that page, it is written, that is an apache server,so to access next flag change robots.txt to .htaccess , ull find 4th part(3s_2_lO0k). There it is written,i love making websites on mac, i can store a lot of info there, this is the difficult part and my writeup told that it can be access through DS_Store, change the link to .DS_Store, ull get the part 5(_35844447}) and this is the end of this challenge.
Flag:picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}

