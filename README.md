# autoArchive
Xcode自动打包并上传至蒲公英或AppStore

SCHEME：一般为当前运行工程名；

CODE_SIGN_IDENTITY:发布证书；

ADHOC_PROVISIONING_PROFILE：adhoc包配置文件；

APPSTORE_PROVISIONING_PROFILE：AppStore包配置文件；

//配置文件查找方式：Xcode->prefrences->account->provisingprofile->showinfinder->粘贴；

ADHOC_EXPORT_OPTIONS：adhoc包相关配置；

APPSTORE_EXPORT_OPTIONS：提交AppStore相关配置；

USER_KEY（line20），API_KEY（line21）：蒲公英账号唯一的，可去个人账号中查询；

APPSTORE_USER_KEY(line24),APPSTORE_USER_PASSWORD(linear5):appstore账号和密码；
  

###命令，以workspace为例：
- 仅打adhoc包

```python3 ./autobuild.py -w youproject.xcworkspace -o /fileName -i ipa -c adhoc```

- 仅打appstore包

```python3 ./autobuild.py -w youproject.xcworkspace -o /fileName -i ipa -e appstore```

- 打adhoc包并并上传至蒲公英

```python3 ./autobuild.py -w youproject.xcworkspace -o /fileName -c adhoc```

- 打appstore包并上传至appstore

```python3 ./autobuild.py -w youproject.xcworkspace -o /fileName -e appstore```

- 同时打adhoc包和AppStore包，不上传

```python3 ./autobuild.py -w youproject.xcworkspace -o /fileName -i ipa -c adhoc -e appstore```

- 已存在ipa上传至蒲公英[-u upload]

```python3 ./autobuild.py -o ./youproject.ipa -u upload```

- 已存在ipa上传至AppStore[-a altool]

```python3 ./autobuild.py -o ./youproject.ipa -a altool```
