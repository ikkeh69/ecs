# CreateDeploymentSet {#doc_api_999647 .reference}

Creates a deployment set in the specified region.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Ecs&api=CreateDeploymentSet) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Name|Type|Required|Example|Description|
|----|----|--------|-------|-----------|
|RegionId|String|Yes|cn-hangzhou| The ID of the region where the deployment set resides. You can call [DescribeRegions](~~25609~~) to view the latest regions of Alibaba Cloud.

 |
|Action|String|No|CreateDeploymentSet| The operation that you want to perform. Set the value to CreateDeploymentSet.

 |
|ClientToken|String|No|123e4567-e89b-12d3-a456-426655440000| A client token. It is used to ensure the idempotency of requests. The value of this parameter is generated by the client and is unique among different requests. The **ClientToken** parameter must be no more than 64 ASCII characters in length. For more information, see [How to ensure idempotency](~~25693~~).

 |
|DeploymentSetName|String|No|FinanceDeployment| The name of the deployment set. It must be 2 to 128 characters in length. It must start with a letter and cannot start with http:// or https://. It can contain letters, digits, colons \(:\), underscores \(\_\), and hyphens \(-\).

 |
|Description|String|No|FinanceJoshua| The description of the deployment set. It must be 2 to 256 characters in length. It cannot start with http:// or https://.

 |
|Domain|String|No|Default| The deployment domain.

 Default value: Default.

 **Note:** This parameter will be removed in the future. We recommend that you use other parameters to ensure compatibility.

 |
|Granularity|String|No|Host| The deployment granularity.

 **Note:** This parameter will be removed in the future. We recommend that you use other parameters to ensure compatibility.

 |
|OnUnableToRedeployFailedInstance|String|No|CancelMembershipAndStart| The emergency solution to redeploy failed instances in the deployment set. Valid values:

 -   CancelMembershipAndStart: restarts the instances immediately after they are shut down and migrated to other deployment sets. This is the default value.
-   KeepStopped: keeps the instances shut down and restarts them after the deployment set is replenished.

 |
|Strategy|String|No|StrictDispersion| The deployment strategy.

 **Note:** This parameter will be removed in the future. We recommend that you use other parameters to ensure compatibility.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example|Description|
|----|----|-------|-----------|
|DeploymentSetId|String|ds-bp1frxuzdg87zh4pzqkcm| The ID of the deployment set.

 |
|RequestId|String|473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E| The ID of the request.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}
https://ecs.aliyuncs.com/?Action=CreateDeploymentSet
&RegionId=cn-hangzhou 
&DeploymentStrategy=Availability
&DeploymentSetName=AvailMySet
&<Common request parameters>
```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<CreateDeploymentSetResponse>
  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
  <DeploymentSetId>ds-bp1frxuzdg87zh4pzqkcm</DeploymentSetId>
</CreateDeploymentSetResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
	"DeploymentSetId": "ds-bp1frxuzdg87zh4pzqkc"
}
```

## Error codes {#section_ggr_gxa_amk .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|MissingParameter|The input parameter RegionId that is mandatory for processing this request is not supplied.|The error message returned when the required RegionId parameter is not specified.|
|400|InvalidDescription.Malformed|The specified parameter Description is not valid.|The error message returned when the value of the Description parameter is invalid. The value must be 2 to 256 characters in length and cannot start with http:// or https://.|
|400|MissingParameter|The input parameter DeploymentSetId that is mandatory for processing this request is not supplied.|The error message returned when the DeploymentSetId parameter is not specified.|

[View error codes](https://error-center.aliyun.com/status/product/Ecs)

