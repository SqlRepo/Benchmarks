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

Each test is run against a SQL database containing 50,000 records. The tests are run 105 times, with the first 5 tests being ignored to allow for JIT and any dynamic IL.

Test Machine is a VM with 4 cores running on an i7 7700k. Last run on [4th March 2018](https://github.com/SqlRepo/Benchmarks/blob/master/RawResults/2018-04-03_18-44.txt).


| Test        | Library           | Best Recorded Test (ms)  | Total Time Taken (ms)  |
| ------------- |:-------------:| -----:| -----:|
Select All Records | Dapper | 51.03ms | 6250.34ms
Select All Records | EF Core | 163.11ms | 19874.59ms
Select All Records | SqlRepo | 50.34ms | 6260.17ms

| Test        | Library           | Best Recorded Test (ms)  | Total Time Taken (ms)  |
| ------------- |:-------------:| -----:| -----:|
Select TOP 1 | Dapper | 0.3ms | 40.43ms
Select TOP 1 | EF Core | 0.66ms | 73.73ms
Select TOP 1 | SqlRepo | 0.35ms | 42.85ms
Select TOP 1 | SqlRepo (Raw SQL with Entity Mapper) | 0.32ms | 40.16ms

| Test        | Library           | Best Recorded Test (ms)  | Total Time Taken (ms)  |
| ------------- |:-------------:| -----:| -----:|
Select TOP 5000 | Dapper | 3.91ms | 533ms
Select TOP 5000 | EF Core | 9.81ms | 2082.93ms
Select TOP 5000 | SqlRepo | 4ms | 526.43ms

| Test        | Library           | Best Recorded Test (ms)  | Total Time Taken (ms)  |
| ------------- |:-------------:| -----:| -----:|
Select DecimalValue From All Records | Dapper | 13.16ms | 2382.85ms
Select DecimalValue From All Records  | EF Core | 39.93ms | 5106.13ms
Select DecimalValue From All Records  | SqlRepo | 12.74ms | 2284.85ms
