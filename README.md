# Example-migration-PostgreSQL-to-PostgreSQL

This is an example showing how to migrate PostgreSQL data to another PostgreSQL service.

## Quick Guide

**STEP1** Login to the PostgreSQL GUI workspace [pgAdmin](https://www.pgadmin.org/download/)

**STEP2** Find your source & target

For example, I have 2 external databases here. I'm going to migrate some data from **f990c75b-** to **7056feb0-**

![Imgur](https://i.imgur.com/TuxBXwD.png)

**STEP3** The source

You may choose to backup the whole database or some certain schemas in your database.

Here, we want to export the schema -- migrate.

![Imgur](https://i.imgur.com/airl7jR.png)

After clicking on backup, there would be a pop-up. Set up the directory of the **`.sql file`** and the format to **`tar`**.

![Imgur](https://i.imgur.com/L4kh6Fe.png)

**STEP4** The target

Go to your target database and restore the **`.sql file`**.

![Imgur](https://i.imgur.com/N9ob4td.png)

Then, set up the directory to your restore file.

![Imgur](https://i.imgur.com/kzrOEk8.png)

Now, this part is important. In PostgreSQL, there are owner and privilege settings. However, in the target database, the owners or owner groups might not exist. Therefore, we change the settings in **restore options**, we **do not save owner and privileges**. You still can alter the owners and privileges later on.

![Imgur](https://i.imgur.com/shotK4r.png)

**STEP5** Post-restore check

Refresh the database to check for update.

![Imgur](https://i.imgur.com/X2WC2gJ.png)

There would also be a pop-up in the right-bottom, click more details to check the logs, or create a simple query to check if the data is successfully migrated.
