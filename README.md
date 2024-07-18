macos 上运行nginx遇见了403问题，是权限不足导致的
在nginx.conf文件中配置serve内容
sudo nano /opt/homebrew/etc/nginx/nginx.conf

user root owner;
location / {
        root   /Users/yuna/frontend-project/nginx-1.20.2/html/sky; #这里的目录要指向index.html的目录
        index  index.html index.htm;
        autoindex on; # 用于调试目录结构，调试后可以删除
    }

 然后sudo nginx -s reload 就解决了
