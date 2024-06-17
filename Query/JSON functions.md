JSON_EXTRACT_ARRAY:</br>
WITH</br>
  input AS (</br>
  SELECT</br>
    '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]' AS json</br>
  UNION ALL</br>
  SELECT</br>
    '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]' )</br>
SELECT</br>
  record</br>
FROM</br>
  input,</br>
  UNNEST(JSON_EXTRACT_ARRAY(json)) record;</br>
</br></br>
JSON_EXTRACT_SCALAR:</br>
WITH input AS (</br>
  SELECT '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]' as json UNION ALL</br>
  SELECT '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]'</br>
)</br>
SELECT </br>
  JSON_EXTRACT_SCALAR(record, "$.COLOUMN1") COLOUMN1,</br>
  JSON_EXTRACT_SCALAR(record, "$.COLOUMN2") COLOUMN2</br>
FROM input, UNNEST(JSON_EXTRACT_ARRAY(json)) record;</br>
