# AWS Glue Interactive Sessions with PyCharm
Working through the following AWS Blog post

https://aws.amazon.com/blogs/big-data/author-aws-glue-jobs-with-pycharm-using-aws-glue-interactive-sessions/

## Resources

https://docs.aws.amazon.com/glue/latest/dg/interactive-sessions.html

https://docs.aws.amazon.com/glue/latest/dg/interactive-sessions-magics.html

https://aws.amazon.com/blogs/big-data/author-aws-glue-jobs-with-pycharm-using-aws-glue-interactive-sessions/

https://www.youtube.com/watch?v=04LMQxDxjGM

### Configure the glue kernel

https://aws.amazon.com/blogs/big-data/introducing-aws-glue-interactive-sessions-for-jupyter/

```shell
%region – Region
%profile – AWS CLI profile
%iam_role – IAM role for the AWS Glue service role
%worker_type – Worker type
%number_of_workers – Number of workers
%idle_timeout – How long to allow a session to idle before stopping it
%additional_python_modules – Python libraries to install from pip
```


## Setup

### Create python virtual environment

### Pip install dependencies
in terminal window:

`pip install pip-tools`

Create requirements.in and add:
```
jupyter
boto3
aws-glue-sessions
```
Then execute:

```
pip-compile
pip install -r requirements.txt
```

### Install kernelspecs for jupyter

find the local site-packages directory, cd to it, and run the jupyter kernelspec install commands

```
cd `pip show aws-glue-sessions | grep Location | awk '{print $2}'`
cd aws_glue_interactive_sessions_kernel
jupyter kernelspec install glue_pyspark
jupyter kernelspec install glue_spark      
```


### Update .aws/configuration

Make sure you create an AWS profile for the account you want to use


# AWS Local Dev

https://github.com/sardetushar/awsglue-pycharm-local-dev

