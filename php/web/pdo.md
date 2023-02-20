#PDO
this is the new way of working with database in php with object oriented programming.

**P**ortable **D**atabase **O**..

The use of PDO class is much simpler than in other methods

	$conn = new PDO("mysql:hostlocalhost;dbname=Tut", "user", "Password");
	$stmt = $conn->query("select * from Tut");
	//loop the items
	while ($row = $stmt->fetch(PDO::FETCH_ASSOC){
		echo $row;
	};