 -- ALTER TABLE actividad MODIFY COLUMN id_status  int(11) UNSIGNED NOT NULL;
 -- ALTER TABLE classroom.actividad ADD CONSTRAINT fk_actividad_status FOREIGN KEY (id_status) REFERENCES  classroom.status(id);

-- SELECT concat( 'ALTER TABLE ',TABLE_SCHEMA,'.',TABLE_NAME,' MODIFY COLUMN `',COLUMN_NAME,'`  int(11) UNSIGNED NOT NULL;' ) 
FROM information_schema.COLUMNS  
WHERE TABLE_SCHEMA IN ('classroom')
AND COLUMN_NAME like 'id_%' 
AND SUBSTR(TABLE_NAME,1,2) <> 'vw'

-- SELECT concat( 'ALTER TABLE ',TABLE_SCHEMA,'.',TABLE_NAME,
               ' ADD CONSTRAINT fk_',TABLE_NAME,'_',SUBSTR(COLUMN_NAME,4), 
               ' FOREIGN KEY (',COLUMN_NAME,')',
               ' REFERENCES  ', TABLE_SCHEMA,'.',SUBSTR(COLUMN_NAME,4),'(id);' ) 
FROM information_schema.COLUMNS  
WHERE TABLE_SCHEMA IN ('classroom')
AND COLUMN_NAME like 'id_%' 
AND SUBSTR(TABLE_NAME,1,2) <> 'vw'

