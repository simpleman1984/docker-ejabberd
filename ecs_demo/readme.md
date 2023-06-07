mkdir database
# 后台
docker run -d --name ejabberd -v $(pwd)/ejabberd.yaml:/home/ejabberd/conf/ejabberd.yml -v $(pwd)/database:/home/ejabberd/database -p 5222:5222 ejabberd/ecs
# 前台
docker run --rm --name ejabberd -v $(pwd)/ejabberd.yaml:/home/ejabberd/conf/ejabberd.yml -v $(pwd)/database:/home/ejabberd/database -p 5222:5222 -p 5280:5280 77e8610de3a0