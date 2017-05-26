# Azure 2.0 Command Line

## Web Apps

list all web apps

`az appservice web list`

get settings for a web app

`az appservice web config appsettings show --resource-group mysites --name site123`

update a setting for a web app

`az appservice web config appsettings update -g mysites -n site123 --settings LOREMIPSUM=5`