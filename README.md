sails-i18n
==========

本文来自：[这里](http://sailsjs.org/#/documentation/concepts/Internationalization)

Sails依赖：[i18n-node](https://github.com/mashpie/i18n-node#list-of-configuration-options)支持检测user language和数据字典

#### 使用

*. 在view里面

```
<h1> <%= __('Hello') %> </h1>
```


*. json语言文件

config/locales/es.json

```
{
    "Hello!": "Hola!"
}
```



#### 配置

[更多参考](https://github.com/balderdashy/sails-docs/blob/master/reference/sails.config/sails.config.i18n.md)

config/i18n.js


代码示例：

```
module.exports.i18n = {
	locales: ['en', 'es', 'fr', 'de'],
	defaultLocale: 'en',
	localesDirectory: '/config/locales'
}
```


| Property           | Type        | Default               | Details |
|--------------------|:-----------:|-----------------------|---------|
| `locales`          | ((array))   | ['en','es','fr','de'] | 支持的语言标记 [locale codes](http://en.wikipedia.org/wiki/BCP_47)
| `localesDirectory` | ((string))  | '/config/locales'     | 设置那些语言资源文件的路径 (i.e. stringfiles)
| `defaultLocale`    | ((string))  | 'en'                  | The default locale for the site. Note that this setting will be overridden for any request that sends an "Accept-Language" header (i.e. most browsers), but it's still useful if you need to localize the response for requests made by non-browser clients (e.g. cURL).
| `updateFiles`      | ((boolean)) | false                 | Whether to automatically add new keys to locale (translation) files when they are encountered during a request.

