## Act 1

Exercise to explore Node's [FileSystem API][filesystem-api].

### Getting Started
- Create a file called `act1.js`, which you are going to execute via `node`.
- You are free to organize your code into multiple files as you choose fit.


### Exercise
- Write a function that reads the config file `config.json` using one of the functions listed in the [FileSystem API][filesystem-api].
  - The function should handle a failure scenario - if the config file does not exist, it should log the error, and exit the program
  - The config contains an important parameter called `cereal-type`.
- Read the file `data.csv` using the Node FileSystem API's [asynchronous function](https://nodejs.org/api/fs.html#fs_fs_readfile_file_options_callback)
  - If the environment variable `SYNC` is set, use Node FileSystem API's [synchronous function](https://nodejs.org/api/fs.html#fs_fs_readfilesync_file_options) to read the `data.csv` file.
- Parse the CSV file, and filter out all the rows that don't match the `cereal-type` listed in the config
- Write a function called `cerealConsciousness` which groups the cereals based on the following rules:
  - `low-risk`:
    - If `sugars` column is less than 5
  - `medium-risk`:
    - If `sugars` column is between 5 & 10
  - `heart-attack`
    - If `sugars` column is greater than 10
  - The function should finally return the cereals grouped like so -
    ```bash
    {"low-risk": [ .... ], // array containing names of all the cereals with low risk
    "medium-risk": [ .... ], // array containing names of all the cereals with medium risk
    "heart-attack": [ .... ]}
    ```

### How to run the program
The program can be executed in the following ways
```bash
node act1.js
```
```bash
SYNC=true node act1.js
```

### Expected output
- The output of running the command above in the terminal should return the following
```bash1
{"low-risk": [ .... ],
 "medium-risk": [ .... ],
 "heart-attack": [ .... ]}
 ```

[filesystem-api]: https://nodejs.org/api/fs.html
