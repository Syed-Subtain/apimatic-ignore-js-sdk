# Simple Calculator

```ts
const simpleCalculatorController = new SimpleCalculatorController(client);
```

## Class Name

`SimpleCalculatorController`


# Get Calculate

Calculates the expression using the specified operation.

```ts
async getCalculate(
  operation: OperationTypeEnum,
  x: number,
  y: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<OperationTypeEnum>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `operation` | [`OperationTypeEnum`](../../doc/models/operation-type-enum.md) | Template, Required | The operator to apply on the variables |
| `x` | `number` | Query, Required | The LHS value |
| `y` | `number` | Query, Required | The RHS value |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [OperationTypeEnum](../../doc/models/operation-type-enum.md).

## Example Usage

```ts
const collect = {
  operation: OperationTypeEnum.MULTIPLY,
  x: 222.14,
  y: 165.14
}

try {
  const { result, ...httpResponse } = await simpleCalculatorController.getCalculate(collect);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

