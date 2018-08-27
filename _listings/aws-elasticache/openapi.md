swagger: "2.0"
x-collection-name: AWS ElastiCache
x-complete: 1
info:
  title: AWS ElastiCache API
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=CreateCacheCluster:
    get:
      summary: Create Cache Cluster
      description: Creates a cache cluster.
      operationId: createCacheCluster
      x-api-path-slug: actioncreatecachecluster-get
      parameters:
      - in: query
        name: AuthToken
        description: Reserved parameter
        type: string
      - in: query
        name: AutoMinorVersionUpgrade
        description: This parameter is currently disabled
        type: string
      - in: query
        name: AZMode
        description: Specifies whether the nodes in this Memcached cluster are created
          in a single Availability Zone or             created across multiple Availability
          Zones in the clusters region
        type: string
      - in: query
        name: CacheClusterId
        description: The node group (shard) identifier
        type: string
      - in: query
        name: CacheNodeType
        description: The compute and memory capacity of the nodes in the node group
          (shard)
        type: string
      - in: query
        name: CacheParameterGroupName
        description: The name of the parameter group to associate with this cache
          cluster
        type: string
      - in: query
        name: CacheSecurityGroupNames.CacheSecurityGroupName.N
        description: A list of security group names to associate with this cache cluster
        type: string
      - in: query
        name: CacheSubnetGroupName
        description: The name of the subnet group to be used for the cache cluster
        type: string
      - in: query
        name: Engine
        description: The name of the cache engine to be used for this cache cluster
        type: string
      - in: query
        name: EngineVersion
        description: The version number of the cache engine to be used for this cache
          cluster
        type: string
      - in: query
        name: NotificationTopicArn
        description: The Amazon Resource Name (ARN) of the Amazon Simple Notification
          Service (SNS) topic           to which notifications are sent
        type: string
      - in: query
        name: NumCacheNodes
        description: The initial number of cache nodes that the cache cluster has
        type: string
      - in: query
        name: Port
        description: The port number on which each of the cache nodes  accepts connections
        type: string
      - in: query
        name: PreferredAvailabilityZone
        description: The EC2 Availability Zone in which the cache cluster is created
        type: string
      - in: query
        name: PreferredAvailabilityZones.PreferredAvailabilityZone.N
        description: A list of the Availability Zones in which cache nodes are created
        type: string
      - in: query
        name: PreferredMaintenanceWindow
        description: Specifies the weekly time range during which maintenance            on
          the cache cluster is performed
        type: string
      - in: query
        name: ReplicationGroupId
        description: Important
        type: string
      - in: query
        name: SecurityGroupIds.SecurityGroupId.N
        description: One or more VPC security groups associated with the cache cluster
        type: string
      - in: query
        name: SnapshotArns.SnapshotArn.N
        description: A single-element string list containing an Amazon Resource Name
          (ARN) that uniquely identifies a Redis RDB snapshot file stored in Amazon
          S3
        type: string
      - in: query
        name: SnapshotName
        description: The name of a Redis snapshot from which to restore data into
          the new node group (shard)
        type: string
      - in: query
        name: SnapshotRetentionLimit
        description: The number of days for which ElastiCache retains automatic snapshots
          before deleting them
        type: string
      - in: query
        name: SnapshotWindow
        description: The daily time range (in UTC) during which ElastiCache begins
          taking a daily snapshot of your node group (shard)
        type: string
      - in: query
        name: Tags.Tag.N
        description: A list of cost allocation tags to be added to this resource
        type: string
      responses:
        200:
          description: OK
      tags:
      - Cache Clusters
  /?Action=DeleteCacheCluster:
    get:
      summary: Delete Cache Cluster
      description: Deletes a previously provisioned cache cluster.
      operationId: deleteCacheCluster
      x-api-path-slug: actiondeletecachecluster-get
      parameters:
      - in: query
        name: CacheClusterId
        description: The cache cluster identifier for the cluster to be deleted
        type: string
      - in: query
        name: FinalSnapshotIdentifier
        description: The user-supplied name of a final cache cluster snapshot
        type: string
      responses:
        200:
          description: OK
      tags:
      - Cache Clusters
  /?Action=DescribeCacheClusters:
    get:
      summary: Describe Cache Clusters
      description: |-
        Returns information about all provisioned
                    cache clusters if no cache cluster identifier is specified, or about a specific cache
                    cluster if a cache cluster identifier is supplied.
      operationId: describeCacheClusters
      x-api-path-slug: actiondescribecacheclusters-get
      parameters:
      - in: query
        name: CacheClusterId
        description: The user-supplied cluster identifier
        type: string
      - in: query
        name: Marker
        description: An optional marker returned from a prior request
        type: string
      - in: query
        name: MaxRecords
        description: The maximum number of records to include in the response
        type: string
      - in: query
        name: ShowCacheNodeInfo
        description: An optional flag that can be included in the DescribeCacheCluster
          request             to retrieve information about the individual cache nodes
        type: string
      responses:
        200:
          description: OK
      tags:
      - Cache Clusters
  /?Action=ModifyCacheCluster:
    get:
      summary: Modify Cache Cluster
      description: Modifies the settings for a cache cluster.
      operationId: modifyCacheCluster
      x-api-path-slug: actionmodifycachecluster-get
      parameters:
      - in: query
        name: ApplyImmediately
        description: If true, this parameter causes the modifications in this request
          and any            pending modifications to be applied, asynchronously and
          as soon as possible, regardless            of the PreferredMaintenanceWindow
          setting for the cache cluster
        type: string
      - in: query
        name: AutoMinorVersionUpgrade
        description: This parameter is currently disabled
        type: string
      - in: query
        name: AZMode
        description: Specifies whether the new nodes in this Memcached cache cluster
          are all created in a             single Availability Zone or created across
          multiple Availability Zones
        type: string
      - in: query
        name: CacheClusterId
        description: The cache cluster identifier
        type: string
      - in: query
        name: CacheNodeIdsToRemove.CacheNodeId.N
        description: A list of cache node IDs to be removed
        type: string
      - in: query
        name: CacheNodeType
        description: A valid cache node type that you want to scale this cache cluster
          up to
        type: string
      - in: query
        name: CacheParameterGroupName
        description: The name of the cache parameter group to apply to this cache
          cluster
        type: string
      - in: query
        name: CacheSecurityGroupNames.CacheSecurityGroupName.N
        description: A list of cache security group names to authorize on this cache
          cluster
        type: string
      - in: query
        name: EngineVersion
        description: The upgraded version of the cache engine to be run on the cache
          nodes
        type: string
      - in: query
        name: NewAvailabilityZones.PreferredAvailabilityZone.N
        description: The list of Availability Zones where the new Memcached cache
          nodes are created
        type: string
      - in: query
        name: NotificationTopicArn
        description: The Amazon Resource Name (ARN) of the Amazon SNS topic to which
          notifications are sent
        type: string
      - in: query
        name: NotificationTopicStatus
        description: The status of the Amazon SNS notification topic
        type: string
      - in: query
        name: NumCacheNodes
        description: The number of cache nodes that the cache cluster should have
        type: string
      - in: query
        name: PreferredMaintenanceWindow
        description: Specifies the weekly time range during which maintenance   on
          the cluster is performed
        type: string
      - in: query
        name: SecurityGroupIds.SecurityGroupId.N
        description: Specifies the VPC Security Groups associated with the cache cluster
        type: string
      - in: query
        name: SnapshotRetentionLimit
        description: The number of days for which ElastiCache retains automatic cache
          cluster snapshots before            deleting them
        type: string
      - in: query
        name: SnapshotWindow
        description: The daily time range (in UTC) during which ElastiCache  begins
          taking a daily snapshot of            your cache cluster
        type: string
      responses:
        200:
          description: OK
      tags:
      - Cache Clusters
  /?Action=RebootCacheCluster:
    get:
      summary: Reboot Cache Cluster
      description: |-
        Reboots some, or all, of the cache nodes
                    within a provisioned cache cluster.
      operationId: rebootCacheCluster
      x-api-path-slug: actionrebootcachecluster-get
      parameters:
      - in: query
        name: CacheClusterId
        description: The cache cluster identifier
        type: string
      - in: query
        name: CacheNodeIdsToReboot.CacheNodeId.N
        description: A list of cache node IDs to reboot
        type: string
      responses:
        200:
          description: OK
      tags:
      - Cache Clusters