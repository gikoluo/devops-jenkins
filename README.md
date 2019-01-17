# README

## 系统管理

### 认证配置
为了支持多角色管理，需要设置Jenkins的登录机制为LDAP。 设置方法见： docs/ldap.png

### 获得plugins
1. 访问：http://127.0.0.1:8080/script
2. 粘贴代码：
```
List<String> jenkinsPlugins = new ArrayList<String>(Jenkins.instance.pluginManager.plugins);
jenkinsPlugins.sort { it.displayName }
              .each { plugin ->
                   println ("${plugin.shortName}:${plugin.version}")
              }
```
3. 运行，获得结果，更新到plugins.txt中


