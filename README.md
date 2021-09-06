sudo chmod a+rwx ebin/
# MOD_OFFLINE_HTTP_POST MODULE UPDATE FOR THE VERSION 19

it works from version 18.09 to 19.09, idk if works in version 19.09+
### Take from:
- see: [github](https://github.com/badlop/mod_offline_http_post/tree/master)
- see: [stackoverflow](https://stackoverflow.com/questions/61918443/custom-module-in-ejabberd-is-not-called)

And Update to the latest version and works with Content-Type: `application/json`

### How to Install:

1)  Locate The Ejabberd-contrib-module on your system:
    - some examples of where it might be found are:
        - if you installed ejabberd from the github repository or the website:
            - `/opt/ejabberd-19.02/.ejabberd-module/`
        - If you installed Ejabberd via the RPM or APT package:
            - `/var/lib/ejabberd/.ejabberd-modules/`

            - **NOTE**: If you installed ejabberd from the package manager of your linux architecture (RPM, APT ...) and you cannot get the folder, you must do some extra steps:

                1) Install the ejabberd-contrib-module package:
                    - on Debian/Ubuntu:
                        - `sudo apt-get install ejabberd-contrib`
                2) then you must install any package so that the folder is created for you, I recommend you follow this [tutorial](https://docs.ejabberd.im/developer/extending-ejabberd/modules/#managing-your-own-modules), which is extremely simple 
2) Enter to the source directory and make git clone of the repository:
```console
root@server:/var/lib/ejabberd/.ejabberd-modules/sources/# git clone -b version19 https://github.com/Carlososuna11/mod_offline_http_post.git 
```
**Note**: remember to change the branch so that version 19 can be installed

3) install module:
    - if you installed ejabberd from the github repository or the website:
    ```console
    root@server:opt/ejabberd-19.02/.ejabberd-module/bin/# ejabberdctl module_install mod_offline_http_post
    ```
    - If you installed Ejabberd via the RPM or APT package:
    ```console
    root@server:~# ejabberdctl module_install mod_offline_http_post
    ```

4) restart ejabberd

**NOTE**: If you have problems installing since it appears that you cannot create or write a file in the ebin folder, simply in the folder that we have cloned we create the ebin folder and we give it permissions that anyone can create / modify it:
```console
sudo chmod a+rwx ebin/
```
