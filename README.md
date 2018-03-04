# Benchmarks
This repository contains the .NET application for running the SqlRepo performance benchmarks. The aim is to use realistic scenarios to compare performance.

## Compared Libraries
* SqlRepo
* Dapper
* EF Core 2.0

*Please note*
All benchmark results should be taken with a pinch of salt as there are many ways to write queries, and many ways to use each ORM. There are many factors to consider when choosing which library to use, such as timing, memory allocation and strong typing.

We welcome any feedback to the benchmarks, and any contributions to add other libraries to compare through a pull request.

## Results

Each test is run against a SQL database containing 250k records. The tests are run 100 times and the best result is used.

Test Machine is a VM with 2 cores running on an i7 7700k. Last run on 4th March 2018.


| Test        | Library           | Time Taken (ms)  |
| ------------- |:-------------:| -----:|
Select All Records | Dapper | 259ms
Select All Records | EF Core | 890ms
Select All Records | SqlRepo | 262ms

| Test        | Library           | Time Taken (ms)  |
| ------------- |:-------------:| -----:|
Select TOP 5000 | Dapper | 4.07ms
Select TOP 5000 | EF Core | 12.87ms
Select TOP 5000 | SqlRepo | 4.04ms
