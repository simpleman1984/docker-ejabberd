mkdir database
# 后台
docker run -d --name ejabberd -v $(pwd)/ejabberd.yaml:/home/ejabberd/conf/ejabberd.yml -v $(pwd)/database:/home/ejabberd/database -p 5222:5222 ejabberd/ecs
# 前台
docker run --rm --name ejabberd -v $(pwd)/ejabberd.yaml:/home/ejabberd/conf/ejabberd.yml -v $(pwd)/database:/home/ejabberd/database -p 5222:5222 -p 5280:5280 93861e42064f

# 官方仓库
https://docs.ejabberd.im/admin/installation/#docker-image
https://github.com/simpleman1984/docker-ejabberd