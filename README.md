# 分布式系统实验作业

## 开发环境

使用 `conda`（或 `mamba`）创建环境：

```shell shell
conda create -n py3.10.5 python=3.10.5 pip=24.0
```

进入环境并安装项目需要的包：

```shell shell
conda activate py3.10.5
pip install -r requirements.txt
```

加载环境变量：

```shell shell
source dev.env

# 一般的 shell 直接上面这样就行，这里我在 linux 上开发，
# 使用的 shell 是 fish，export 环境变量的方式稍微不同
# source fish.env
```

在 `config/default.py` 中，修改超管账号，为自己的腾讯蓝鲸账号 `username`：

```python python
INIT_SUPERUSER = ['username'] 
```

另外我的 URL 中将设置超管账号的 `/set-su` 改成了 `setsu`，因为我用 `curl` 调试的时候发现 `-` 好像出问题，不知道为啥）

## 调试与运行

```shell shell
# 使用腾讯开发框架的东西需要 migrate
python manage.py makemigrations
python manage.py migrate

# 运行
python manage.py runserver
```