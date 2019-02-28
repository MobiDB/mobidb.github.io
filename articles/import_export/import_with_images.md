# Import with images, attached files #

> [!WARNING]
> Currently only Android app supports csv import with images.

In order to import data with images/files we've added additional functionality to CSV import.

In order to import with images csv file should contain column with images path, for example:

*Name, Position, **Photo**, Birth date, Phone, Email, About, Skype*
Sarah Jones, Sales
Manager, **Employees_images/53a867af54a5418ca17de2168b18ab74.jpeg**, 1/25/1983,407-555-5963,sarahjones@gmail.com, "Hobbies: yoga & stretching, reading, travelling (Europe, South America) Has 2 daughters (Lisa, 2004 and Marie, 2008). Likes big cars and small dogs.  ", Sarah.Jones
James Morrison, Financial director, **Employees_images/23bcb076175d4048b171d69737e5decc.jpeg**, 3/2/1971, 407-555-6314, jmorrison@gmail.com, "Hobbies: golf, squash, swimming, travelling. His wife is a famous stylist. His son Robert studies in Harward. Likes sportcars  (BMW)", J.Morrison

...

In the folder where csv file reside should be **Employees_images** folder with files specified in csv:

<img src="../../images/csv_import/images.png" style="width:500px"/>

Now you can use [csv import](csv_import.md) to import data with images:

<img src="../../images/csv_import/picture.png" style="width:500px"/>

You can also choose **File** type instead of **Picture**.

Results can be found below:

<img src="../../images/csv_import/result.png" style="width:500px"/>
