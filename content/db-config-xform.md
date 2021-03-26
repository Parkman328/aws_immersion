---
title: Step 4 - Configure a Transformation
section: Database-to-Database Replication
tutorialtype: replicate
permalink: /replicate/tutorial/db-config-xform.php
---

The transformation we will create in this section will:

* Add a new column **fullName** to the **Player** target table
* Populate that column with values from other columns in the table.

To get started, `double click` on the **Player** table in the **Selected Tables** frame.

![Tranform 1 Image](/images/xform-1.png)

Then click on the `Transform` button.

![Tranform 2 Image](/images/xform-2.png)

And click on `Add Column`.

![Tranform 3 Image](/images/xform-3.png)

Call the new column `fullName`,

![Tranform 4 Image](/images/xform-4.png)

and change its default type from **STRING(50)** to `WSTRING(100)`. You can get a dropdown of 
valid types you can choose by clicking the **type** column next to **fullName**.

![Tranform 5 Image](/images/xform-5.png)

Note though, that the default precision of the WSTRING type is 50 ... we will need more space
than that due to the width of some of the data we will be working with, so you will need to 
type `WSTRING(100)` into the **type** column.

![Tranform 5a Image](/images/xform-5a.png)

Now we need to define the transformation we want to use to populate the column. Click on `fx` to
bring up the trasformation **Expression Builder**.

![Tranform 6 Image](/images/xform-6.png)

The expression we are going to build will involve concatenating three columns, _nameGiven_, 
_nameFirst_, and _nameLast_ into a column called _fullName_. Start by double clicking 
`nameGiven` which will put **$nameGiven** into the expression builder.

![Tranform 7 Image](/images/xform-7.png)

Now press the concatenation operator `||` and add the string `' ('.

![Tranform 8 Image](/images/xform-8.png)

and repeat those steps with `nameFirst` and `nameLast` until you have an expression that looks like

<p align="center">
<b>$nameGiven||' ('||$nameFirst||') '||$nameLast</b>
</p>

Note that you could just as easily have typed the the expression in directly, or even 
copied and pasted it from this web page.

![Tranform 9 Image](/images/xform-9.png)

Now click the `Parse Expression` button and enter the data:

* $nameGiven: `first middle`
* $nameFirst: `nickname`
* $nameLast: `lastname`


![Tranform 10 Image](/images/xform-10.png)

and press the `Test Expression` button.  This process allows us to put test values in 
the columns that make up the expression and validate that the output looks as we expect it to.

![Tranform 11 Image](/images/xform-11.png)

Assuming your output looks like the output indicated (**first middle (nickname) lastname**), 
your transformation is correct. Press `OK` to save the transfomration and return to the
previous screen.

![Tranform 12 Image](/images/xform-12.png)

You will note below that we can see that there is now an expression next to the **fullName** column.
If you hover your mouse over that column you will be able to inspect the transformation without
having to click into it. Press `OK` again to return to the previous screen.

![Tranform 13 Image](/images/xform-13.png)

Notice the word **(Changed)** next to the _testdrive.Player_ column. This indicates that
a transformation has been defined that alters the state of the data as it moves from the
source to the target.

![Tranform 14 Image](/images/xform-14.png)

That is it for configuration. We are now ready to save our task and run it. Press `Save` at the top
left of the window.

**Optional:** If you want to check that your Postgres Target has no data loaded please check 

SQLPad by accesing __http://YOUR_SERVER_IP_ADDRESS:3000__ 

Only Table you should see is table called test and no new data.

![SQLPad Default Image](/images/prod/sqlpad-default.png)

Now Press `Run` Button

![Postgres Task 4 Image](/images/postgres-task-4.png)

# [NEXT](../db-run-task)