# LAB2 - Family Trip

In this repository I propose a TSP solution using Evolutionary Algorithm

| Country | Population Size | Mutation Rate | Num Elites | Num Generations | Final Cost  | Known Solution |
| ------- | --------------- | ------------- | ---------- | --------------- | ----------- | -------------- |
| china   | 20              | 0.5           | 2          | 50              | 877373.82km | inf            |
| italy   | 50              | 0.4           | 3          | 200             | 6473.74km   | 4172.76        |
| russia  | 50              | 0.4           | 3          | 200             | 131595.99km | 32722.5        |
| us      | 50              | 0.4           | 3          | 200             | 326431.43km | 39016.59       |
| vanuatu | 50              | 0.4           | 3          | 7               | 1345.54km   | 1345.54        |


## Visualizing the Algorithm
While running the code produce snapshot of each generation and finally produce a video out of those snapshot in 30fps (30 generation per second)
To speedup the visualization an array is preallocated with the right dimension of dimension `(rows=NUM_GENERATIONS, column=NUM_CITIES + 1)` (the +1 is because of the redundant city at the first and last position used to make the travel return to the starting point)

Each generation calculate the best path and append that to the preallocated array. 

If you don't have enough RAM or just want to speedup the execution and don't care about visualizing the evolution (shame) you can comment every line where the `best_evolution` is used and also comment the parallelize the lines where the `save_solution` is used

While writing this README I'm using the joblib to speedup only this part, a lot of speedup can be achieved by applying parallelize job in different part (mutation, reproduction, ...). 

If you're concerned about what this library do (as the professor does explicit said anything about it yet) you can find more [here](https://joblib.readthedocs.io/en/latest/index.html).

The snapshots and videos are stored respectively under the `imgs` and `out` folders

From github those folder won't be present as uploading 500 generation or large video file would be useless as they are procedurally created by running the code
> !ATTENTION!<br>
> Consider the following metrics for the file generated:<br>
> Single screenshot ~= 100KB<br>
> 500 generation ~= 500MB video<br>


If you are interested in watching the evolution through the ages just run the code and wait for it to finishes (hope you have enough free storage :P)
> !ATTENTION!<br>
> Consider running the notebook from the start as one of the first step is to sterilize the output folder:<br>
> create if not existent or deleting all files/folders inside of them