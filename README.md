NOTE: this is a fork from https://github.com/mantisadnetwork/heroku-buildpack-maxmind. It only deals with the free downloadable databases from MaxMind.

# MaxMind Build Pack
Ensure your application has the latest copy of MaxMind's GeoLite2 free downloadable databases when deploying. Ideally, you should have a way to restart your application to make sure this build back happens often enough (if you deploy daily/weekly, you have nothing to worry about).

## How it Works
The database file(s) is saved to a Heroku cache directory that is persisted across builds. If the database file does not exist, or is older than a day, a new copy is downloaded and moved to your project before deployment. All database files are stored in the root of your project when deployed.

## Required Environment Variables
* MAXMIND_EDITIONS = Comma delimited list of databases to download ie: "GeoLite2-City,GeoLite2-Country"
* MAXMIND_KEY = License key necessary to download MaxMind GeoLite2 databases.
* MAXMIND_FORCE = Force clearing the cache if set

## How to Use
Follow the instructions at https://github.com/ddollar/heroku-buildpack-multi for using multiple build packs. Simply add this repository to this list and voila!
