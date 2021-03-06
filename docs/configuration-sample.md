# Configuration sample file

The following is a production configuration file, with some details redacted.

```json
{
  "Debug": true,
  "EnableSyslog": false,
  "ListenAddress": ":3000",
  "MySQLTopologyCredentialsConfigFile": "/etc/mysql/orchestrator.cnf",
  "MySQLTopologySSLPrivateKeyFile": "",
  "MySQLTopologySSLCertFile": "",
  "MySQLTopologySSLCAFile": "",
  "MySQLTopologySSLSkipVerify": true,
  "MySQLTopologyUseMutualTLS": false,
  "MySQLTopologyMaxPoolConnections": 3,
  "MySQLOrchestratorHost": "127.0.0.1",
  "MySQLOrchestratorPort": 3306,
  "MySQLOrchestratorDatabase": "orchestrator",
  "MySQLOrchestratorCredentialsConfigFile": "/etc/mysql/orchestrator_srv.cnf",
  "MySQLOrchestratorSSLPrivateKeyFile": "",
  "MySQLOrchestratorSSLCertFile": "",
  "MySQLOrchestratorSSLCAFile": "",
  "MySQLOrchestratorSSLSkipVerify": true,
  "MySQLOrchestratorUseMutualTLS": false,
  "MySQLConnectTimeoutSeconds": 1,
  "DefaultInstancePort": 3306,
  "ReplicationLagQuery": "select round(absolute_lag) from meta.heartbeat_view",
  "SlaveStartPostWaitMilliseconds": 1000,
  "DiscoverByShowSlaveHosts": false,
  "InstancePollSeconds": 5,
  "ReadLongRunningQueries": false,
  "SkipMaxScaleCheck": true,
  "BinlogFileHistoryDays": 10,
  "UnseenInstanceForgetHours": 240,
  "SnapshotTopologiesIntervalHours": 0,
  "InstanceBulkOperationsWaitTimeoutSeconds": 10,
  "ActiveNodeExpireSeconds": 5,
  "HostnameResolveMethod": "default",
  "MySQLHostnameResolveMethod": "@@hostname",
  "SkipBinlogServerUnresolveCheck": true,
  "ExpiryHostnameResolvesMinutes": 60,
  "RejectHostnameResolvePattern": "",
  "ReasonableReplicationLagSeconds": 10,
  "ProblemIgnoreHostnameFilters": [

  ],
  "VerifyReplicationFilters": false,
  "MaintenanceOwner": "orchestrator",
  "ReasonableMaintenanceReplicationLagSeconds": 20,
  "MaintenanceExpireMinutes": 10,
  "MaintenancePurgeDays": 365,
  "CandidateInstanceExpireMinutes": 60,
  "AuditLogFile": "",
  "AuditToSyslog": false,
  "AuditPageSize": 20,
  "AuditPurgeDays": 365,
  "RemoveTextFromHostnameDisplay": ":3306",
  "ReadOnly": false,
  "AuthenticationMethod": "",
  "HTTPAuthUser": "",
  "HTTPAuthPassword": "",
  "AuthUserHeader": "",
  "PowerAuthUsers": [
    "*"
  ],
  "ClusterNameToAlias": {
    "127.0.0.1": "test suite"
  },
  "AccessTokenUseExpirySeconds": 60,
  "AccessTokenExpiryMinutes": 1440,
  "DetectClusterAliasQuery": "select ifnull(max(cluster_name), '') as cluster_alias from meta.cluster where anchor=1",
  "DetectClusterDomainQuery": "",
  "DataCenterPattern": "",
  "DetectDataCenterQuery": "select 'redacted'",
  "PhysicalEnvironmentPattern": "",
  "PromotionIgnoreHostnameFilters": [

  ],
  "ServeAgentsHttp": false,
  "UseSSL": false,
  "UseMutualTLS": false,
  "SSLSkipVerify": false,
  "SSLPrivateKeyFile": "",
  "SSLCertFile": "",
  "SSLCAFile": "",
  "SSLValidOUs": [

  ],
  "StatusEndpoint": "/api/status",
  "StatusSimpleHealth": true,
  "StatusOUVerify": false,
  "HttpTimeoutSeconds": 60,
  "StaleSeedFailMinutes": 60,
  "SeedAcceptableBytesDiff": 8192,
  "PseudoGTIDPattern": "drop view if exists `meta`.`_pseudo_gtid_hint__asc:",
  "PseudoGTIDPatternIsFixedSubstring": true,
  "PseudoGTIDMonotonicHint": "asc:",
  "DetectPseudoGTIDQuery": "select count(*) as pseudo_gtid_exists from meta.pseudo_gtid_status where anchor = 1 and time_generated > now() - interval 1 day",
  "PseudoGTIDPreferIndependentMultiMatch": true,
  "BinlogEventsChunkSize": 10000,
  "BufferBinlogEvents": true,
  "SkipBinlogEventsContaining": [
    "@@SESSION.GTID_NEXT= 'ANONYMOUS'"
  ],
  "ReduceReplicationAnalysisCount": false,
  "FailureDetectionPeriodBlockMinutes": 60,
  "RecoveryPollSeconds": 2,
  "RecoveryPeriodBlockSeconds": 600,
  "RecoveryIgnoreHostnameFilters": [

  ],
  "RecoverMasterClusterFilters": [
    "*"
  ],
  "RecoverIntermediateMasterClusterFilters": [
    "*"
  ],
  "OnFailureDetectionProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'detection' -f '{failureType}' -h '{failedHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}'"
  ],
  "PreFailoverProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'pre-failover' -f '{failureType}' -h '{failedHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}'"
  ],
  "PostFailoverProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'post-failover' -f '{failureType}' -h '{failedHost}' -H '{successorHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}' -u '{recoveryUID}'"
  ],
  "PostUnsuccessfulFailoverProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'post-unsuccessful-failover' -f '{failureType}' -h '{failedHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}' -u '{recoveryUID}'"
  ],
  "PostMasterFailoverProcesses": [
    "/redacted/do-something # e.g. kick pt-heartbeat on promoted master"
  ],
  "PostIntermediateMasterFailoverProcesses": [

  ],
  "CoMasterRecoveryMustPromoteOtherCoMaster": true,
  "DetachLostSlavesAfterMasterFailover": true,
  "ApplyMySQLPromotionAfterMasterFailover": true,
  "MasterFailoverLostInstancesDowntimeMinutes": 60,
  "PostponeReplicaRecoveryOnLagMinutes": 10,
  "OSCIgnoreHostnameFilters": [

  ],
  "GraphitePollSeconds": 60,
  "GraphiteAddr": "",
  "GraphitePath": "",
  "GraphiteConvertHostnameDotsToUnderscores": true,
  "BackendDB": "mysql",
  "MySQLTopologyReadTimeoutSeconds": 3,
  "MySQLDiscoveryReadTimeoutSeconds": 3,
  "SQLite3DataFile": "/var/lib/orchestrator/orchestrator-sqlite.db",
  "RaftEnabled": false,
  "RaftBind": "redacted",
  "RaftDataDir": "/var/lib/orchestrator",
  "DefaultRaftPort": 10008,
  "ConsulAddress": "redacted:8500",
  "RaftNodes": [
    "redacted",
    "redacted",
    "redacted"
  ]
}
{
  "Debug": true,
  "EnableSyslog": false,
  "ListenAddress": ":3000",
  "MySQLTopologyCredentialsConfigFile": "/etc/mysql/orchestrator.cnf",
  "MySQLTopologySSLPrivateKeyFile": "",
  "MySQLTopologySSLCertFile": "",
  "MySQLTopologySSLCAFile": "",
  "MySQLTopologySSLSkipVerify": true,
  "MySQLTopologyUseMutualTLS": false,
  "MySQLTopologyMaxPoolConnections": 3,
  "DatabaselessMode__experimental": false,
  "MySQLOrchestratorHost": "127.0.0.1",
  "MySQLOrchestratorPort": 3306,
  "MySQLOrchestratorDatabase": "orchestrator",
  "MySQLOrchestratorCredentialsConfigFile": "/etc/mysql/orchestrator_srv.cnf",
  "MySQLOrchestratorSSLPrivateKeyFile": "",
  "MySQLOrchestratorSSLCertFile": "",
  "MySQLOrchestratorSSLCAFile": "",
  "MySQLOrchestratorSSLSkipVerify": true,
  "MySQLOrchestratorUseMutualTLS": false,
  "MySQLConnectTimeoutSeconds": 1,
  "DefaultInstancePort": 3306,
  "ReplicationLagQuery": "select round(absolute_lag) from meta.heartbeat_view",
  "SlaveStartPostWaitMilliseconds": 1000,
  "DiscoverByShowSlaveHosts": false,
  "InstancePollSeconds": 5,
  "ReadLongRunningQueries": false,
  "SkipMaxScaleCheck": true,
  "BinlogFileHistoryDays": 10,
  "UnseenInstanceForgetHours": 240,
  "SnapshotTopologiesIntervalHours": 0,
  "InstanceBulkOperationsWaitTimeoutSeconds": 10,
  "ActiveNodeExpireSeconds": 5,
  "HostnameResolveMethod": "default",
  "MySQLHostnameResolveMethod": "@@hostname",
  "SkipBinlogServerUnresolveCheck": true,
  "ExpiryHostnameResolvesMinutes": 60,
  "RejectHostnameResolvePattern": "",
  "ReasonableReplicationLagSeconds": 10,
  "ProblemIgnoreHostnameFilters": [

  ],
  "VerifyReplicationFilters": false,
  "MaintenanceOwner": "orchestrator",
  "ReasonableMaintenanceReplicationLagSeconds": 20,
  "MaintenanceExpireMinutes": 10,
  "MaintenancePurgeDays": 365,
  "CandidateInstanceExpireMinutes": 60,
  "AuditLogFile": "",
  "AuditToSyslog": false,
  "AuditPageSize": 20,
  "AuditPurgeDays": 365,
  "RemoveTextFromHostnameDisplay": ":3306",
  "ReadOnly": false,
  "AuthenticationMethod": "",
  "HTTPAuthUser": "",
  "HTTPAuthPassword": "",
  "AuthUserHeader": "",
  "PowerAuthUsers": [
    "*"
  ],
  "ClusterNameToAlias": {
    "127.0.0.1": "test suite"
  },
  "AccessTokenUseExpirySeconds": 60,
  "AccessTokenExpiryMinutes": 1440,
  "DetectClusterAliasQuery": "select ifnull(max(cluster_name), '') as cluster_alias from meta.cluster where anchor=1",
  "DetectClusterDomainQuery": "",
  "DataCenterPattern": "",
  "DetectDataCenterQuery": "select 'redacted'",
  "PhysicalEnvironmentPattern": "",
  "PromotionIgnoreHostnameFilters": [

  ],
  "ServeAgentsHttp": false,
  "UseSSL": false,
  "UseMutualTLS": false,
  "SSLSkipVerify": false,
  "SSLPrivateKeyFile": "",
  "SSLCertFile": "",
  "SSLCAFile": "",
  "SSLValidOUs": [

  ],
  "StatusEndpoint": "/api/status",
  "StatusSimpleHealth": true,
  "StatusOUVerify": false,
  "HttpTimeoutSeconds": 60,
  "StaleSeedFailMinutes": 60,
  "SeedAcceptableBytesDiff": 8192,
  "PseudoGTIDPattern": "drop view if exists `meta`.`_pseudo_gtid_hint__asc:",
  "PseudoGTIDPatternIsFixedSubstring": true,
  "PseudoGTIDMonotonicHint": "asc:",
  "DetectPseudoGTIDQuery": "select count(*) as pseudo_gtid_exists from meta.pseudo_gtid_status where anchor = 1 and time_generated > now() - interval 1 day",
  "PseudoGTIDPreferIndependentMultiMatch": true,
  "BinlogEventsChunkSize": 10000,
  "BufferBinlogEvents": true,
  "SkipBinlogEventsContaining": [
    "@@SESSION.GTID_NEXT= 'ANONYMOUS'"
  ],
  "ReduceReplicationAnalysisCount": false,
  "FailureDetectionPeriodBlockMinutes": 60,
  "RecoveryPollSeconds": 2,
  "RecoveryPeriodBlockSeconds": 600,
  "RecoveryIgnoreHostnameFilters": [

  ],
  "RecoverMasterClusterFilters": [
    "*"
  ],
  "RecoverIntermediateMasterClusterFilters": [
    "*"
  ],
  "OnFailureDetectionProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'detection' -f '{failureType}' -h '{failedHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}'"
  ],
  "PreFailoverProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'pre-failover' -f '{failureType}' -h '{failedHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}'"
  ],
  "PostFailoverProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'post-failover' -f '{failureType}' -h '{failedHost}' -H '{successorHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}' -u '{recoveryUID}'"
  ],
  "PostUnsuccessfulFailoverProcesses": [
    "/redacted/our-orchestrator-recovery-handler -t 'post-unsuccessful-failover' -f '{failureType}' -h '{failedHost}' -C '{failureCluster}' -A '{failureClusterAlias}' -n '{countSlaves}' -u '{recoveryUID}'"
  ],
  "PostMasterFailoverProcesses": [
    "/redacted/do-something # e.g. kick pt-heartbeat on promoted master"
  ],
  "PostIntermediateMasterFailoverProcesses": [

  ],
  "CoMasterRecoveryMustPromoteOtherCoMaster": true,
  "DetachLostSlavesAfterMasterFailover": true,
  "ApplyMySQLPromotionAfterMasterFailover": true,
  "MasterFailoverLostInstancesDowntimeMinutes": 60,
  "PostponeReplicaRecoveryOnLagMinutes": 10,
  "OSCIgnoreHostnameFilters": [

  ],
  "GraphitePollSeconds": 60,
  "GraphiteAddr": "",
  "GraphitePath": "",
  "GraphiteConvertHostnameDotsToUnderscores": true,
  "BackendDB": "mysql",
  "MySQLTopologyReadTimeoutSeconds": 3,
  "MySQLDiscoveryReadTimeoutSeconds": 3,
  "SQLite3DataFile": "/var/lib/orchestrator/orchestrator-sqlite.db",
  "RaftEnabled": false,
  "RaftBind": "redacted",
  "RaftDataDir": "/var/lib/orchestrator",
  "DefaultRaftPort": 10008,
  "ConsulAddress": "redacted:8500",
  "RaftNodes": [
    "redacted",
    "redacted",
    "redacted"
  ]
}
```
