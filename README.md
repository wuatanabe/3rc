# R3c
Rest Redmine Ruby Client

## Setup

gem install R3c

## Usage

### Set Redmine URL

R3c.site('http://localhost:3000/')

### Set format

R3c.format(:xml)

###Use API KEY

R3c.auth({api: {key: '8091d55257c4c90b6d56e83322622cb5f4ecee64'}})


###Prepare to create an issue with an attachment

file = File.read('c:\windows-version.txt')
token = R3c.upload file
issue_params= {"project_id"=> 1, "subject"=> "This is the subject"}
issue_params["uploads"]= [{"upload"=>{"token"=> token, "filename"=> "R3c.gemspec", "description"=> "a gemspec", "content_type"=> "text/plain"}}]

###Create issue

issue= R3c.issue.create(issue_params )

###Retrive projects

projects= R3c.project.all

See code for other examples