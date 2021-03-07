# mysql_sys.ps_check_lost_instrumentation-

SELECT 
    `performance_schema`.`global_status`.`VARIABLE_NAME` AS `variable_name`,
    `performance_schema`.`global_status`.`VARIABLE_VALUE` AS `variable_value`
FROM
    `performance_schema`.`global_status`
WHERE
    ((`performance_schema`.`global_status`.`VARIABLE_NAME` LIKE 'perf%lost')
        AND (`performance_schema`.`global_status`.`VARIABLE_VALUE` > 0))
