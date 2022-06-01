
# CoinCap API ETL Pipeline - Dagster-ized

In this project we will used Dagster to orchestration and ETL Pipeline. 
You can read the [article]() on this. :smile:

## Objective
Simply fetch the list of Crypto Exchanges from [CoinCap API](https://docs.coincap.io/#aff336c8-9d06-4654-bc15-a56cef06a69e), enrich & transform the data and store in PostgreSQL database for further use (eg. Analytics, Visualization, etc )

## Usage
### Setup
- Create `.conf.ini` as a duplicate of `.conf_sample.ini` & update with your PostgreSQL Database credentials:
```bash
cp .conf_sample.ini .conf.ini
```

- Install Python Dependencies (It's preferable to use a virtual environment):
```bash
pip3 install -r requirements.txt
```

- Setup database. (This drops then recreate the schema & tables):
```bash
python3 setup.py
```
#### Run ETL using `dagit` (Web UI)
- Run the command below to run the `dagit` (Dagster UI Component) on http://localhost:3000:
```bash
dagit -f run_etl.py
```
- Then click on `Launchpad`
  - ![Click on Launchpad](https://github.com/mikekenneth/coincap_etl_dagster/raw/main/img/img4.png "Click on Launchpad")
- Then click on `Launch Run` (lower right corner) to trigger the job
  - ![Click on Launch Run](https://github.com/mikekenneth/coincap_etl_dagster/raw/main/img/img5.png "Click on Launch Run")

#### Run ETL using `dagster` (CLI)

- Run the command below to run the ETL job directly

  ```bash
  dagster job execute -f run_etl.py
  ```

### Tech Stack
- [Python3](https://www.python.org/)
- [PostgreSQL](https://www.postgresql.org/)
- [Dagster](https://www.dagster.io/)


## TO-DO
- [x] Make the ETL functional as a python script
- [x] Add A Batch ID and Datetime
- [x] Design & Documentation
- [x] Add Dagster as Workflow Orchestrator
- [ ] Add Docker: Make the project easily deployable


## Authors
- [@mikekenneth](https://www.github.com/mikekenneth)


## License
[MIT](https://choosealicense.com/licenses/mit/)


## Credits
See as you fit.

## Contact
If you have any questions or would like to get in touch, please open an issue on GitHub or send me an email: <mike.kenneth47@gmail.com>