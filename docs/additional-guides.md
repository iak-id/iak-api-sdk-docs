# Additional Guides

In this section, we provide you this additional guides to help you develop and connecting your application to our libraries or SDK.

## Sandbox report

We provide you this feature, Sandbox Report, to help you see the development transaction status, both for prepaid and postpaid. You can see this feature on [our developer website](https://developer.iak.id/sandbox-report).

For prepaid service, because the transaction status will not change automatically, you must change it manually in this Sandbox Report. You can see how to use this service for prepaid by seeing [here](https://api.iak.id/docs/platform/docs/integration/sandbox-report.md#prepaid).

For postpaid service, you can not change the transaction status in Sandbox Report like can, because you must do payment after inquiry to see the changed status. You can see how to use this service for postpaid by seeing [here](https://api.iak.id/docs/platform/docs/integration/sandbox-report.md#postpaid).

## Callback

For prepaid service, besides check the transaction status regularly, you can use our callback service. So, when the transaction status changes automatically in the production state or manually on the development state, you can receive the response that filled with the changed status and don't have to check the transaction status regularly.

You can see how to use this callback service by seeing [here](https://api.iak.id/docs/reference/docs/prepaid/callback.md).