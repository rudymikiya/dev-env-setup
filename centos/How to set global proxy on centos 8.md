1. "vi /etc/profile"

PROXY_URL="http://192.168.1.99:7890/"

export http_proxy="$PROXY_URL"

export https_proxy="$PROXY_URL"

export ftp_proxy="$PROXY_URL"

export no_proxy="localhost,127.*,10.*,172.16.*,172.17.*,172.18.*,172.19.*,172.20.*,172.21.*,172.22.*,172.23.*,172.24.*,172.25.*,172.26.*,172.27.*,172.28.*,172.29.*,172.30.*,172.31.*,192.168.*"

2. "source /etc/profile"
