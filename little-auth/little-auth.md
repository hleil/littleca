# litte-auth

## 项目介绍
little-auth 基于littleca的认证服务 
1. little-auth-core 核心依赖包
2. little-auth-service 认证服务
   token实现参见 com.taoyuanx.auth.SimpleTokenManager
   支持 多种hmac 算法，和rsa，支持国密sm3
   


## api简介
1.  认证接口（/auth）
2. token刷新接口（/auth/refresh）  
3. 用户信息获取接口  
参见com.taoyuanx.ca.auth.controller
## 认证设计
1. 接入账户提前申请，由管理端分配 apiAccount 和 apiSecret 或 apiAccount，并交换公钥）
2. 认证请求参数(AuthRequestDTO)：json(random,apiAccount,timestamp,sign)  
    基于 apiAccount+时间戳+签名（公私钥）验证请求方身份

## 请求参数构造
参见：com.taoyuanx.test.LittleAuthRequestTest  