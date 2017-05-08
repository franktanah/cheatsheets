#### FORM POST with file
curl -F c=@myfile.txt https://ptpb.pw/

#### FORM POST using STDOUT of another process
echo post-this | curl -F c=@- https://ptpb.pw/

#### API / POST JSON
curl -s http://localhost:8080/ -d '{ "say_hello": { "name": "Eileen", "times": 4 } } ' | python -m json.tool