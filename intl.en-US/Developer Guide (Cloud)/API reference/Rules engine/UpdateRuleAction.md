# UpdateRuleAction {#reference_zjs_1kd_xdb .reference}

You can call this operation to modify the specified rule action.

## Request parameters {#section_rl5_nz1_ydb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to UpdateRuleAction.|
|ActionId|Long|Yes|The ID of the rule action to be modified.|
|Type|String|Yes| The rule actions type. Values include:

 DATAHUB: Transfers the data in the topics that have been processed by the rules engine to the Alibaba Cloud DataHub for stream computing.

 ONS: Transfers the data in the topics that have been processed by the rules engine to the Alibaba Cloud Message Queue for messages distribution.

 MNS: Transfers the data in the topics that have been processed by the rules engine to the Alibaba Cloud Message  Service \(MNS\) for message transmission.

 FC: Transfers the data in topics that have been processed by the rules engine to the Alibaba Function Compute service for events statistics.

 OTS: Transfers the data in topics that have been processed by the rules engine to the Alibaba Table Store service for NoSQL database storage.

 REPUBLISH: Forwards the data in topics that have been processed by the rules engine to another IoT topic.

 **Note:** 

-   The FC type is not available in Singapore, where the endpoint is ap-southeast. 
-   The DATAHUB, FC, and ONS types are not available in US \(Sillicon Valley\), where the endpoint is us-west-1.
-   Rules in binary data format \(the value of DataType is BINARY\) do not support OTS.

 |
|Configuration|String|Yes|The configuration of the specified rule action. The configurations for different rule action types are different. For more information, see the descriptions for each type in [CreateRuleAction](reseller.en-US/Developer Guide (Cloud)/API reference/Rules engine/CreateRuleAction.md#section_ev2_m5z_xdb).|

## Response parameters {#section_ctr_z1b_ydb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The GUID generated by Alibaba Cloud for the request.|
|Success|Boolean|Indicate whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.|
|ErrorMessage|String|The error message returned when the call fails.|

## Examples {#section_g1c_dbb_ydb .section}

**Request example**

```
https://iot.cn-shanghai.aliyuncs.com/?Action=UpdateRuleAction
&ActionId=10003
&Type=REPUBLISH
&Configuration={"topic":"/a1********/device5/get"}
&<common request parameters>
```

**Response example**

```
{
    "RequestId": "21D327AF-A7DE-4E59-B5D1-ACAC8C024555",
    "Success": true
}
```
