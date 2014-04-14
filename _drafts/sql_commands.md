SELECT 
   CONCAT(
     "DROP TABLE ",  
      GROUP_CONCAT(TABLE_NAME)
    ) AS stmt 
    FROM information_schema.TABLES 
    WHERE TABLE_SCHEMA = "<database name>" AND TABLE_NAME LIKE "<something>_%";


SELECT GROUP_CONCAT(
		CONCAT(
			"RENAME TABLE ", table_name, " TO <something>_", table_name
			) SEPARATOR ";"
			) 
			FROM information_schema.tables 
			WHERE table_schema = "<database name>" AND table_name LIKE "<something>_%";
