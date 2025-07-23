# dotnet-otel
after you clone the repository 


``cd elk
docker-compose up -d ``


then maybe in another terminal go to myapp/WebApplication1 and dotnet run

` dotnet run `

now hit to the endpoint to generate logs

` curl http://localhost:5283/weatherforecast `

now first check docker logs of otel collector to see you are able to successfully send logs from your app to the otel collector docker instance:

` docker logs -f elk-otel-collector-1 ` 

you should see some logs like:

" Body: Str(This is a log message from OpenTelemetry logger.)" 

Now let set up elasticsearch:

go to kibana instance in `localhost:5601`

you may click explore my own button

then go to discover

click create data view button

enter index pattern: ` logs-generic.otel-*`

set name as `otel logs` or anything you like

then click "save data view to kibana`