# How to: export a pdb database schema (mind Licencing!)
su - oracle
// select name from V$database;
export DB_NAME=/<global-db-name/>  
// select * from v$pdbs;
export ORACLE_PDB_SID=/<pdb-name/>
export GU_ID=/<pdb-guid/>
export COMPRESSION=all
export today=$(date +%Y%m%d)

export SCHEMA=/<schema-name/>
expdp \"/ as sysdba\" directory=data_pump_dir \
dumpfile="${SCHEMA}_${today}.dmp" logfile="${SCHEMA}_${today}_exp.log" \
schemas=${SCHEMA} compression=${COMPRESSION} -reuse_dumpfiles

# How to: Gather DB information
// show the global db name
select name from V$database;
OR
select * from global_name;

// show pdb information (e.g. guid)
select * from v$pdbs;