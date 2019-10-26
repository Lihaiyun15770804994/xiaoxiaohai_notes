### 一.Flask初始化

- ```
  # 1,导入Flask的类
  from flask import Flask, render_template

  # 2,实例化Flask的类
  # __name__的作用:指定个本文件同级的目录就是根目录
  # 默认的静态文件存储位置，就是根目录下的static文件夹
  # 默认的静态文件访问地址欠前缀就是/static
  # 默认提供的模板的存放位置是 根目录下的 templates

  # 修改静态文件访问的路径前缀，通过配置static_url_path来指定，注意前面一定要加上 `/`
  # 修改静态文件存储的位置，通过static_folder来指定
  # 修改模板的存放位置，通过template_folder来指定
  app = Flask(__name__)
  ```

- ```
  配置的使用方式
  # 1,通过配置文件加载
  # app.config.from_pyfile('config.ini')

  # 2，通过对象来加载
  # 要创建一个对象
  # class Config:
  #     DEBUG = True
  from settings import Config
  app.config.from_object(Config)

  # 3，直接定义app.config， app.config是一个类字典形式的对象
  # app.config['DEBUG'] = True



  # 获取配置信息
  # print(app.config['NAME'])
  ```

- ```
  # 3，定义路由，定义视图函数
  # 4, 需要装饰器来定义路由，通过app.route(路由地址)
  @app.route('/')
  def index():

      # 4，返回响应
      return 'hello world'

      # 5,渲染模板
      # return render_template('index.html')
  ```

- ```
  if __name__ == '__main__':

      # 启动flask
      # app.run(host='0.0.0.0', port='8888', debug=True)
      app.run()
  ```

  ### 

#### 路由

- ​