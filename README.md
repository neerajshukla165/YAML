# YAML

Hello, and welcome to this topic.

In this topic, we take a look at what YAML files are. All Ansible playbooks are written in YAML.

If you have worked with other data structure formats like XML or JSON, you should be able to easily pick it up.

Don't worry. If you haven't worked on any of these, you should still be able to easily pick it up.

Going through the coding exercises that accompany this page.

## Introduction

A YAML file is used to represent data, in this case, configuration data.

Here is a quick comparison of a sample data in three different formats.

The one on the left is XML where we display a list of servers and their information.

The same data is represented in JSON format in the middle, and finally, in YAML format to the right.

Take a minute to compare the three formats.

```
XML                                       JSON                              YAML
<Servers>                              {                                 Servers:
  <Server>                                Servers: [                        -  name: Server1  
    <Name>Server1</name>                    {                                  owner: John
    <owner>John</owner>                     name: Server1,                     created: 12232012
    <created>12232012</created>             owner:John,                        status: active
    <Status>active</active>                 created: 12232012,
  </Server>                                 status: active,
</Servers>                                  }
                                          ]
                                        }  
  
 ```
 
