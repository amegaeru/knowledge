```
export const handler = async(event) => {
	const response ={
		statusCodde: 200,
		body: JSON.stringify('Hello from Lambda!'),
	};
	return response;
}
```
