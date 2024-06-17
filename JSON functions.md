JSON_EXTRACT_ARRAY:
WITH
  input AS (
  SELECT
    '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]' AS json
  UNION ALL
  SELECT
    '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]' )
SELECT
  record
FROM
  input,
  UNNEST(JSON_EXTRACT_ARRAY(json)) record;

JSON_EXTRACT_SCALAR:
WITH input AS (
  SELECT '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]' as json UNION ALL
  SELECT '[{"RECORD1"},{"RECORD2"},...{"RECORDn"}]'
)
SELECT 
  JSON_EXTRACT_SCALAR(record, "$.COLOUMN1") COLOUMN1,
  JSON_EXTRACT_SCALAR(record, "$.COLOUMN2") COLOUMN2
FROM input, UNNEST(JSON_EXTRACT_ARRAY(json)) record;