# egg-app

## 配置文件

需要添加自己的config.default文件，本人的没上传

module.exports = appInfo => {
  return {
    site: {
      base: xxx, // 项目基础地址
      secret: xxx, // jwt 加密盐
      grant_type: 'authorization_code', // 微信小程序登录验证路径参数
      appid: xxx, // 微信小程序appid
      wxsecret: xxx,
      wxlogin: xxx,// 微信小程序登录验证地址
    },
    // includeApi,
    // excludeApi,
    qiniu: {
      ak: xxx, // Access Key
      sk: xxx, // Secret Key
      zone: 'Zone_z2', // Zone_z0 华东, Zone_z1 华北, Zone_z2 华南, Zone_na0 北美
      bucket: 'camplus-plus',
    },
    keys: appInfo.name + '_1541055266564_8039', // use for cookie sign key, should change to your own and keep security
    middleware: [ 'errorHandler', 'auth', 'aop' ], // add your config here
    auth: {
      ignore: [], // jwt 忽略路径
    },
    aop: {
      enable: false,
      match: [], // aop 拦截路径
    },
    mysql: {
      client: {
        host: 'localhost',
        port: '3306',
        user: xxx,
        password: xxx,
        database: xxx,
      },
    },
    security: {
      csrf: false,
    },
    joi: {
      options: {},
      locale: {
        'zh-cn': {},
      },
      throw: true, // when capture exception throw immediately
      // throwHandle: (error) => { return error; }, // when throw is true the error message format
      // errorHandle: (error) => { return error; }, // when throw is false the error message format
      // resultHandle: (result) => { return result; } // fromat result
    },
  };
};

### 快速启动命令

```bash
$ npm i
$ npm run dev
$ open http://localhost:7001/
```