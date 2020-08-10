
select event_object_schema as database_name,
       event_object_table as table_name,
       trigger_name,
       action_order,
       action_timing,
       event_manipulation as trigger_event,
       action_statement as 'definition'
from information_schema.triggers 
where trigger_schema not in ('sys','mysql')
order by database_name,
         table_name;
