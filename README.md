# codeigniter
update_batch with multiple where condition

# Try 1 :

```
    function update_attendance_batch($list) {
         $this->db->update_batch('student_attendance',$list,'rfid,date');  
         return $this->db->affected_rows();
    }
```

# Error :
```
A Database Error Occurred

One or more rows submitted for batch updating is missing the specified index.

Filename: C:\wamp\www\school\system\database\DB_active_rec.php

Line Number: 1423
```

# Try 2 :
```
    function update_attendance_batch($list) {
         $this->db->update_batch('student_attendance',$list,array('rfid','date')); 
         return $this->db->affected_rows();
    }
```

# Error :
```
A Database Error Occurred

One or more rows submitted for batch updating is missing the specified index.

Filename: C:\wamp\www\school\system\database\DB_active_rec.php

Line Number: 1423
```

# Solution :

>= Codeigniter_2.2.2

Delete : codeigniter_project/system/database/DB_active_rec.php

Now Download below link and paste / replace file

https://github.com/parthviroja/codeigniter/blob/master/DB_active_rec.php

# Try :
```
    function update_attendance_batch($list) {
         $this->db->update_batch('student_attendance',$list,array('rfid','date')); 
         return $this->db->affected_rows();
    }
```

# Result :

3 rows affected..



