### 功能说明
* Serverless 工作流集成了视觉智能服务的系列 API，在工作流中可以低成本使用 AI 的能力。本应用展示了如何在工作流中调用视觉智能 API 进行身份证识别。通过传入的图片地址，Serverless 工作流通过调用身份识别 API，识别出传入身份证图片的人员名称、性别及身份证号。在这个过程中您不需要编写任何代码。您也可以扩展该工作流，对识别结果进行进一步的处理以满足业务需要。

### 文件说明
* template.yml 为模板，负责定义本应用的所需阿里云资源；
* flow/definition.yaml 是工作流文件
    
### 操作步骤

#### 前置条件
* 开通如下服务
    * 视觉智能开放平台-人脸人体服务 [链接](https://vision.aliyun.com/ocr)
    * Serverless 工作流 （Serverless Workflow） [链接](https://www.aliyun.com/product/fnf)
    * 对象存储服务（Object Storage Service，OSS） [链接](https://www.aliyun.com/product/oss)
    * 访问控制（RAM） [链接](https://buy.aliyun.com/ram)

* 本地安装应用部署工具Fun [链接](https://help.aliyun.com/document_detail/140283.html)
    
#### 应用发布

* 发布
    ```bash
     $ fun package -t fun.yaml
     $ fun deploy --use-ros --stack-name test -t template.packaged.yml
    ```

#### 执行应用
在 Serverless 工作流控制台中进入创建的工作流，点击开始执行，并复制以下内容作为输入：
```
{
    "imageUrl": "https://viapi-demo.oss-cn-shanghai.aliyuncs.com/viapi-demo/images/RecognizeIdentityCard/identityCard.jpg"
}
```
