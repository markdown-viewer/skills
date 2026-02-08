# Aws Stencils

Stencil library: `mxgraph.aws.*`

Total: 99 stencils

> **Style hints**
> - 1 outline-only shape(s) — set `fillColor` and `strokeColor` to control appearance
> - 5 shape(s) need `fillColor`+`strokeColor`
> - 85 shape(s) need `fillColor`
>
> **Recommended colors:** fillColor: `#F7981F` / `#3B48CC` / `#E05243` / `#759C3E` / `#262261`

| Shape | Size | Required Styles |
|-------|------|-----------------|
| `mxgraph.aws.compute.cloudwatch` | 53×55 | `fillColor` |
| `mxgraph.aws.compute.cloudwatch_alarm` | 53×60 | `fillColor` |
| `mxgraph.aws.compute.ec2` | 56×57 | `fillColor` |
| `mxgraph.aws.compute.ec2_ami` | 56×57 | `fillColor` |
| `mxgraph.aws.compute.ec2_db_on_instance` | 62×58 | `fillColor` |
| `mxgraph.aws.compute.ec2_elastic_ip` | 37×9 | `fillColor` |
| `mxgraph.aws.compute.ec2_instance` | 56×57 | `fillColor` |
| `mxgraph.aws.compute.ec2_instance_with_cloudwatch` | 56×57 | `fillColor` |
| `mxgraph.aws.compute.ec2_instances` | 58×60 | `fillColor` |
| `mxgraph.aws.compute.elastic_mapreduce` | 57×52 | `fillColor` |
| `mxgraph.aws.compute.elastic_mapreduce_auto_scaling` | 63×63 | `fillColor` |
| `mxgraph.aws.compute.elastic_mapreduce_cluster` | 52×56 | `fillColor` |
| `mxgraph.aws.compute.elastic_mapreduce_hdfs_cluster` | 57×56 | `fillColor` |
| `mxgraph.aws.content_delivery.cloudfront` | 57×57 | `fillColor` |
| `mxgraph.aws.content_delivery.cloudfront_download_distribution` | 58×58 | `fillColor` |
| `mxgraph.aws.content_delivery.cloudfront_edge_location` | 47×47 | `fillColor` |
| `mxgraph.aws.content_delivery.cloudfront_streaming_distribution` | 58×58 | `fillColor` |
| `mxgraph.aws.database.elasticache` | 56×57 | `fillColor` |
| `mxgraph.aws.database.rds` | 49×60 | `fillColor` |
| `mxgraph.aws.database.rds_db_instance` | 62×58 | `fillColor` |
| `mxgraph.aws.database.rds_db_instance_read_replica` | 62×58 | `fillColor` |
| `mxgraph.aws.database.rds_db_instance_standby` | 62×58 | `fillColor` |
| `mxgraph.aws.database.rds_mysql_db_instance` | 62×58 | `fillColor` |
| `mxgraph.aws.database.rds_oracle_db_instance` | 62×58 | `fillColor` |
| `mxgraph.aws.database.simpledb` | 56×55 | `fillColor` |
| `mxgraph.aws.database.simpledb_attribute` | 56×55 | `fillColor` |
| `mxgraph.aws.database.simpledb_attributes` | 54×53 | `fillColor` |
| `mxgraph.aws.database.simpledb_domain` | 56×55 | `fillColor` |
| `mxgraph.aws.database.simpledb_item` | 56×55 | `fillColor` |
| `mxgraph.aws.database.simpledb_items` | 55×53 | `fillColor` |
| `mxgraph.aws.deployment_management.aws_cloudformation` | 48×54 | `fillColor` |
| `mxgraph.aws.deployment_management.aws_cloudformation_stack` | 61×42 | `fillColor` |
| `mxgraph.aws.deployment_management.aws_cloudformation_template` | 48×54 | `fillColor` |
| `mxgraph.aws.deployment_management.aws_elastic_beanstalk` | 64×51 | `fillColor`+`strokeColor` |
| `mxgraph.aws.deployment_management.aws_elastic_beanstalk_applicaton` | 31×54 | `fillColor` |
| `mxgraph.aws.groups.auto_scaling_group` | 59×60 | `fillColor` |
| `mxgraph.aws.groups.availability_zone` | 63×65 | `fillColor` |
| `mxgraph.aws.groups.aws_cloud` | 59×66 |  |
| `mxgraph.aws.groups.aws_cloud_icon` | 17×11 | `fillColor`+`strokeColor` |
| `mxgraph.aws.groups.corporate_data_center` | 59×63 |  |
| `mxgraph.aws.groups.corporate_data_center_icon` | 7×9 | `fillColor`+`strokeColor` |
| `mxgraph.aws.groups.ec2_instance_contents` | 54×57 |  |
| `mxgraph.aws.groups.ec2_spot_instance` | 53×57 |  |
| `mxgraph.aws.groups.elastic_beanstalk_container` | 61×65 |  |
| `mxgraph.aws.groups.elastic_beanstalk_container_icon` | 13×9 | `fillColor`+`strokeColor` |
| `mxgraph.aws.groups.region` | 59×58 | `fillColor` |
| `mxgraph.aws.groups.rrect` | 63×65 | `fillColor` |
| `mxgraph.aws.groups.security_group` | 59×58 | `fillColor`+`strokeColor` (outline) |
| `mxgraph.aws.groups.server_contents` | 57×57 |  |
| `mxgraph.aws.groups.virtual_private_cloud` | 56×63 |  |
| `mxgraph.aws.groups.virtual_private_cloud_icon` | 17×10 | `fillColor` |
| `mxgraph.aws.groups.vpc_subnet` | 58×62 |  |
| `mxgraph.aws.groups.vpc_subnet_icon` | 8×8 | `fillColor` |
| `mxgraph.aws.messaging.ses` | 67×47 | `fillColor` |
| `mxgraph.aws.messaging.ses_email` | 67×47 | `fillColor` |
| `mxgraph.aws.messaging.sns` | 65×44 | `fillColor` |
| `mxgraph.aws.messaging.sns_email_notification` | 67×41 | `fillColor` |
| `mxgraph.aws.messaging.sns_http_notification` | 67×41 | `fillColor` |
| `mxgraph.aws.messaging.sns_topic` | 62×37 | `fillColor` |
| `mxgraph.aws.messaging.sqs` | 59×37 | `fillColor` |
| `mxgraph.aws.messaging.sqs_message` | 36×38 | `fillColor` |
| `mxgraph.aws.messaging.sqs_queue` | 59×36 | `fillColor`+`strokeColor` |
| `mxgraph.aws.misc.aws_cloud` | 40×25 | `fillColor` |
| `mxgraph.aws.misc.virtual_private_cloud` | 40×25 | `fillColor` |
| `mxgraph.aws.misc.vpc_subnet` | 17×18 | `fillColor` |
| `mxgraph.aws.networking.aws_direct_connect` | 55×55 | `fillColor` |
| `mxgraph.aws.networking.elastic_load_balancer` | 57×57 | `fillColor` |
| `mxgraph.aws.networking.route_53` | 60×57 | `fillColor` |
| `mxgraph.aws.networking.route_53_hostedzone` | 58×55 | `fillColor` |
| `mxgraph.aws.networking.route_53_routetable` | 59×50 | `fillColor` |
| `mxgraph.aws.networking.vpc` | 68×42 | `fillColor` |
| `mxgraph.aws.networking.vpc_customer_gateway` | 36×36 | `fillColor` |
| `mxgraph.aws.networking.vpc_internet_gateway` | 36×36 | `fillColor` |
| `mxgraph.aws.networking.vpc_router` | 35×35 | `fillColor` |
| `mxgraph.aws.networking.vpc_vpn_connection` | 65×52 | `fillColor` |
| `mxgraph.aws.networking.vpc_vpn_gateway` | 36×36 | `fillColor` |
| `mxgraph.aws.non_service_specific.aws_management_console` | 57×53 | `fillColor` |
| `mxgraph.aws.non_service_specific.client` | 57×53 | `fillColor` |
| `mxgraph.aws.non_service_specific.corporate_data_center` | 41×54 | `fillColor` |
| `mxgraph.aws.non_service_specific.iam_add_on` | 32×17 | `fillColor` |
| `mxgraph.aws.non_service_specific.internet` | 66×41 | `fillColor` |
| `mxgraph.aws.non_service_specific.mobile_client` | 35×52 | `fillColor` |
| `mxgraph.aws.non_service_specific.multimedia` | 52×48 | `fillColor` |
| `mxgraph.aws.non_service_specific.traditional_server` | 41×54 | `fillColor` |
| `mxgraph.aws.non_service_specific.user` | 46×61 | `fillColor` |
| `mxgraph.aws.non_service_specific.users` | 65×57 | `fillColor` |
| `mxgraph.aws.on_demand_workforce.mechanical_turk` | 66×41 | `fillColor` |
| `mxgraph.aws.on_demand_workforce.mechanical_turk_assignment_task` | 48×54 | `fillColor` |
| `mxgraph.aws.on_demand_workforce.mechanical_turk_hit` | 60×60 | `fillColor` |
| `mxgraph.aws.on_demand_workforce.mechanical_turk_requester` | 41×54 | `fillColor` |
| `mxgraph.aws.on_demand_workforce.mechanical_turk_workers` | 65×57 | `fillColor` |
| `mxgraph.aws.storage.aws_import_export` | 58×59 | `fillColor` |
| `mxgraph.aws.storage.ebs` | 47×60 | `fillColor` |
| `mxgraph.aws.storage.ebs_snapshot` | 53×62 | `fillColor` |
| `mxgraph.aws.storage.ebs_volume` | 47×60 | `fillColor` |
| `mxgraph.aws.storage.s3` | 58×59 | `fillColor` |
| `mxgraph.aws.storage.s3_bucket` | 58×59 | `fillColor` |
| `mxgraph.aws.storage.s3_bucket_with_objects` | 58×59 | `fillColor` |
| `mxgraph.aws.storage.s3_object` | 33×33 | `fillColor` |

## Usage Example

```drawio
<mxfile><diagram id="example" name="Example"><mxGraphModel dx="800" dy="600" grid="1" gridSize="10"><root><mxCell id="0"/><mxCell id="1" parent="0"/><mxCell id="shape1" value="" style="shape=mxgraph.aws.compute.cloudwatch;html=1;fillColor=#F7981F;strokeWidth=2" parent="1" vertex="1"><mxGeometry x="100" y="100" width="60" height="60" as="geometry"/></mxCell></root></mxGraphModel></diagram></mxfile>
```
