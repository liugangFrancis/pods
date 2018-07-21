# pods
常用第三方组件




配置LG

###1.安装pip
sudo yum install python-pip

###2. 使用pip 安装shadowsocks
pip install shadowsocks

### 3. 配置shadowsocks.json文件
{  
   "server":"0.0.0.0",  
   "port_password":{     
        "8388":"password1",  
        "8389":"password2",  
        "443":"password3" 
   }, 
   "timeout":300,  
   "method":"aes-256-cfb",  
   "fast_open":false,
   "workers":1
} 

### 4.启动服务器
ssserver -c/etc/shadowsocks.json -d start

#### 5. 重启
ssserver -c /etc/shadowsocks.json -d restart 

#### 6. 停止
ssserver -c /etc/shadowsocks.json -d stop  


##关键点：开放安全组
在安全组配置的入方向添加安全组规则，此处因为我额外开放了8388以及8389端口，所以添加的安全组规则如图所示：
网卡类型：内网
规则方向：入方向
授权策略：自定义TCP
端口范围：8388/8399
优先级：1
授权类型：地址段访问
授权对象：0.0.0.0/0







