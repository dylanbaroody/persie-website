# Persie's website

## Fixing the font issue

1. Load the website. Right click on the page and select inspect:

![image](https://user-images.githubusercontent.com/72748066/111556175-4dfd7b00-8760-11eb-95d6-5929236fed05.png)

2. Once you are in the chrome console, select the network tab:
 
![image](https://user-images.githubusercontent.com/72748066/111556208-6077b480-8760-11eb-8b86-57752c7cecdd.png)

3. Reload the page. You should see some 404 errors where the fonts can't be found. If you click on the bad request (will be red), you can see the url (Request URL on the top left):

![image](https://user-images.githubusercontent.com/72748066/111556315-a3d22300-8760-11eb-804d-d77ed7857ab1.png)

If this has `localhost:8888` in it, then we can perform the fix we've used before.

4. Open up your ftp client (CyberDuck or FileZilla). Log in to the host `sftp://persiebaroodyphotography.com` on port `22` using the user `dh_wh79g5`. (Password for this user is in `1password`).
5. Once you are connected, we are looking to update 4 files. I have provided safe versions of them in this repo if you want them. The files are:
    - `~/persiewebsite/htdocs/wp-content/uploads/flex/stylekits/custom-ec5b6bbc5390.css`
    - `~/persiewebsite/wp-content/uploads/flex/stylekits/custom-ec5b6bbc5390.css` (This is the one we needed to change on `3/17/21`)
    - `~/persiewebsite/htdocs/wp-content/uploads/flex/stylekits/nomade.css`
    - `~/persiewebsite/wp-content/uploads/flex/stylekits/nomade.css`
6. Check the last updated on any of these files - if they have been updated recently, they might have `localhost:8888` in them. You have two options here:
    a. Download the latest version of each file. Open them up in a text editor (Sublime Text or Notepad), and `ctrl+f` for `localhost:8888`. Replace it with `persiebaroodyphotography.com` wherever you find it in each of these files. Then upload the updated versions.
    b. Just nuke the files with whatever is stored in this repo, which is the safe versions of the files as of `3/17/21`
    
7. Reload the page with the chrome console and confirm that you aren't getting any 404 errors on requests anymore.
