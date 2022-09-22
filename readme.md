## Testing locally
1.	Build the previous custom runtime image using the Docker build command:
```bash 
docker build -t phpmyfunction .
```

2. Run the function locally using the Docker run command, bound to port 9000:
```bash 
docker run -p 9000:8080 phpmyfunction:latest
```

3. This command starts up a local endpoint at `localhost:9000/2015-03-31/functions/function/invocations`


4.	Post an event to this endpoint using a curl command. The Lambda function payload is provided by using the -d flag.  This is a valid Json object required by the Runtime Interface Emulator:

```bash 
curl "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{"queryStringParameters": {"name":"Ben"}}'
```

5. A 200 status response is returned:

![post-oci](../repository-resources/postOCI.png)