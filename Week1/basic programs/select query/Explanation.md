PHP SINGLE SELECT Query - Line by Line Explanation

1) include_once('dbconnect.php'); - Includes
the database connection file. - That file creates a connection variable ($conn) using
mysqli_connect(). - You need this connection to communicate with MySQL.

2) $qry = "select *
from tbemp order by empSal desc"; - Creates an SQL query string. - "select *" means select all
columns. - "order by empSal desc" sorts records by salary (highest first).

 3) $result =
mysqli_query($conn, $qry); - Executes the SQL query. - Sends the query to the MySQL server
using the open connection ($conn). - Stores the returned data (a set of rows) into $result. - Think of
$result as a “box” containing all the rows returned from the database.

 
 4) $row =
mysqli_fetch_array($result); - Fetches the next available row from the $result set. - Converts one
database row into an array ($row). - Each call to mysqli_fetch_array() moves to the next row. - $row
can be accessed using numeric indexes or column names.

5) echo "Records in the Table :"; -
Prints a heading text in HTML.

 6) echo ""; - Starts an HTML table. - border='5' adds border
thickness, cellpadding='8' adds space inside cells.

7) echo ""; - Starts a new table row.
8) echo "".$row[0].""."".$row[1].""."".$row[2].""."".$row[3].""; - Prints one row of data from the fetched
record. - $row[0] → first column (EmpCode) - $row[1] → second column (EmpName) - $row[2] →
third column (EmpCity) - $row[3] → fourth column (EmpSalary)
 9) echo ""; - Ends the table row.
10) echo ""; - Ends the table. 11) mysqli_free_result($result); - Frees the memory associated
with the result set. 12) mysqli_close($conn); - Closes the database connection safely.


■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■ Summary Step | Description | Variable
-----|--------------|----------- 1 | Connect to DB | $conn 2 | Write query | $qry 3 | Execute query | $result
4 | Fetch one row | $row 5 | Display data | $row[0], $row[1], etc. 6 | Free & close | $result, $conn
■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■ Notes: - $result holds all rows from the query. -
mysqli_fetch_array() extracts one row at a time. - $row[] contains the actual data from the database
columns. - If you only want the top result, call my
