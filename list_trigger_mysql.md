Query below lists tables with their triggers.

Query
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
Columns
database_name - name of the table database name
table_name - name of the table
trigger_name - name of the trigger
action_order - the ordinal position of the trigger's action within the list of triggers on the same table with the same trigger_event and action_timing
action_timing - trigger activation time:
before
after
trigger_event - specific SQL operation:
insert
update
delete
definition - SQL definiton of trigger
Rows
One row represents one trigger
Scope of rows: all table triggers in a database
Ordered by database and table name
