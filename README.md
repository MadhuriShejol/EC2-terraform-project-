terraform {
   required_providers {
     aws = {
       source  = "hashicorp/aws"
       version = "6.14.0"
     }
   }
 }

 provider "aws" {
   region = "us-west-2"
 }

 resource "aws_instance" "webserver" {
   ami           = "ami-06a974f9b8a97ecf2"
   instance_type = "t3.micro"
   count = "3"

   tags = {
     Name = "MyInstance"
   }
 }
