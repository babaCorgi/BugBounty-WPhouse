# UploadVuln
任意文件上传(UploadVuln)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**滥用 ACL 权限覆盖其他用户在 s3 存储桶上上传的文件/视频**](https://medium.com/@armaanpathan/abusing-acl-permissions-to-overwrite-other-users-uploaded-files-videos-on-s3-bucket-162c8877728)  
修改Content-Disposition: form-data; name="policy"为html的策略实现文件覆盖形成xss  