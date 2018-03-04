# Benchmarks
This repository contains the .NET application for running the [SqlRepo](https://github.com/SqlRepo/sqlrepo) performance benchmarks. The aim is to use realistic scenarios to compare performance.

## What is SqlRepo?
Find more information about SqlRepo here: [SqlRepo](https://github.com/SqlRepo/sqlrepo)

## Compared Libraries
* [SqlRepo](https://github.com/SqlRepo/sqlrepo)
* Dapper
* EF Core 2.0

*Please note*
All benchmark results should be taken with a pinch of salt as there are many ways to write queries, and many ways to use each ORM. There are many factors to consider when choosing which library to use, such as timing, memory allocation and strong typing.

We welcome any feedback to the benchmarks, and any contributions to add other libraries to compare through a pull request.

## Results

Each test is run against a SQL database containing 250k records. The tests are run 105 times, with the first 5 tests being ignored to allow for JIT and any dynamic IL.

Test Machine is a VM with 4 cores running on an i7 7700k. Last run on 4th March 2018.


| Test        | Library           | Best Recorded Test (ms)  | Total Time Taken (ms)  |
| ------------- |:-------------:| -----:| -----:|
Select All Records | Dapper | Xms | Xms
Select All Records | EF Core | Xms | Xms
Select All Records | SqlRepo | Xms | Xms

| Test        | Library           | Best Recorded Test (ms)  | Total Time Taken (ms)  |
| ------------- |:-------------:| -----:| -----:|
Select TOP 5000 | Dapper | Xms | Xms
Select TOP 5000 | EF Core | Xms | Xms
Select TOP 5000 | SqlRepo | Xms | Xms

| Test        | Library           | Best Recorded Test (ms)  | Total Time Taken (ms)  |
| ------------- |:-------------:| -----:| -----:|
Select DecimalValue From All Records | Dapper | Xms | Xms
Select DecimalValue From All Records  | EF Core | Xms | Xms
Select DecimalValue From All Records  | SqlRepo | Xms | Xms
