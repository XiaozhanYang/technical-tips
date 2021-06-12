1. ssh keys:
	First Name: Xiaozhan
	Last Name: Yang
	Email: xiaozhan.yang@epochtimes.com
	Key password: JiuRen008869*
	Allowed IPs: 82.28.248.213
	Private Key Location on Mac: /Users/codyyang/ssh keys/private_key.txt
	Article Explanation:
        https://www.siteground.com/kb/how_to_log_in_to_my_shared_account_via_ssh_in_mac_os/
        Get private key: https://www.siteground.com/tutorials/ssh/enable-ssh/

	New Key generated on siteground on 4 May 2021
		Name: Xiaozhan's Macbook Pro 13
		Password: JiuRenS008869*

		Hostname: dajiyuan.co.uk
        Username: u1357-ihhdhuowur5v
        Password: The SSH key password
        Port: 18765

2. how to add the private key to local computer:
    method before 4 May 2021:
        1. Copy and save the private key in text file at a specific location of the PC
        2. Run the following command to change permission
            chmod 600 /Users/youruser/private_key
        3. Add the following command to .bash_profile
            ssh-add -K /Users/codyyang/ssh\ keys/private_key.txt
    method after 4 May 2021:
        1. use the key ~/.ssh/id_rsa, which will be autmatically identifed

3. site to check ip address
	https://www.whatismyip.com

4. command for uploading file from local computer to the server (note that the id might have been changed)

	before 4 May 2021: scp -P 18765 -r * dajiyuan@35.214.106.129:public_html/donation
    after 4 May 2021: scp -P 18765 -r * u1357-ihhdhuowur5v@ukm4.siteground.biz:www/donation.dajiyuan.co.uk/public_html/

5. command for connecting server via ssh

	ssh USER@HOST_NAME -pPORT
	before 4 May 2021: ssh dajiyuan@35.214.106.129 -p18765
    after 4 May 2021: ssh u1357-ihhdhuowur5v@dajiyuan.co.uk -p18765
        or: ssh u1357-ihhdhuowur5v@ukm4.siteground.biz -p18765
        or: ssh dajiyuan_siteground
            with configuration in ~/.ssh/config
                Host dajiyuan_siteground
                    Hostname dajiyuan.co.uk
                    User "u1357-ihhdhuowur5v"
                    Port 18765
6. Encrypt SSL
	1. Go to Let's Encrypt page
	2. Select the new address
	3. Click Install button
	4. On the right hand side, Select an Action
		1. Choose HTTPS setting

7. Checkout client-only integration
	1. Ensure that Client-only Integration is enabled.
		Settings > Checkout settings
	1. Add the new address to
		Settings > Checkout settings

8. DNS (domain name system) setting for sending emails from *.dajiyuan.co.uk

	1. at stripe.com, go to: settings > Business settings > emails
	2. at the bottom "email domain", click "add domain"
	3. then click "verify domain", you will see a popup window
	4. at Cpanel of siteground.co.uk, click "Advanced DNS Zone Editor" on the first row
	5. Choose the address dajiyuan.co.uk as domain
	6. Choose TTL as 14400, Name to be the same as "name" on stripe, Address/Txt/Cname to be the same as the "value" on stripe
	7. Note that the Cname value at stripe should be removed.

9. Setting for development
	1. Turn off caching on Siteground, the change can be checked immediately
		1. On the third row "Site Improvement Tools", click SuperCacher
		2. Then turn off the cache for the web address
		3. Remember to turn it back on in production



