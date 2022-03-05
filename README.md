# AeroCMS-Stored_XSS-Poc
* `add_post.php`
![image](https://user-images.githubusercontent.com/79050415/156879687-273b903a-195c-4313-be7a-b4053ecae897.png)
When inserting into the database, the input is not filtered out of html characters
* `post.php`
![image](https://user-images.githubusercontent.com/79050415/156879786-ed53b64e-cf92-4160-aacd-32440b795d32.png)
Even when displaying, the entity cannot be properly encoded
-------------------------------------------------------------
![image](https://user-images.githubusercontent.com/79050415/156879926-c7009ae0-54b5-4b5c-a49f-6c693ce8f2e5.png)
