# AnsibleValheimPlaybook
An Ansible playbook to set up a dedicated Valheim server


Works on:
- Ubuntu 20.04
- Ubuntu 18.04
- Debian 10
- Debian 9

## Variables:
| Variable | default | description |
|---|---|---|
| steam_usr | steamusr | name of the user which is created (not the username in Steam!) |
| valheim_usr | {{ steam_usr }} | name of the user under which the SteamCMD and Valheim server is installed |
| steam_usrs_group | steamgroup | group which the steam user should blong to (will be created) | 
| steam_usr_passwd | {{ lookup('password', 'credentials/' + steam_usr + '/passwd chars=ascii_letters,digits length=128') }}" | password for the Steam user (DON'T use your password in Steam!) |
| pub_ssh_key | id_rsa.pub | name of the PUBLIC ssh keyfile which will be added to the authorized_keys file od the Steam user  |
| valheim_server_name | "ServerName" | name of your Valheim server |
| valheim_server_port | 2456 | port for your Valheim server |
| valheim_server_world | "WorldName" | World name for your Valheim server |
| valheim_server_passwd | "L33tH4ck3rS4f3" | Password for your Valheim server (please change!) |
| valheim_server_savedir | "/home/{{ valheim_usr }}/vhsaves" | directory in witch the world data of your server will be saved |
| valheim_server_vis | 0 | set to 1 if you want your server to be publicly listed |
