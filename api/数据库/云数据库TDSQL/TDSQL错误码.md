TDSQL接口的错误码分为两类：
- 一类是API平台的公共错误码，详见[公共错误码介绍](/doc/api/309/7025)
- 一类是业务自身的错误码，见下表：

| 错误码 | 描述 |
|---------|---------|
| ServiceUnavailable | 没有地区提过 tdsql 服务 |
| NoServiceAvailableForThisRegionId | 请求的 regionId 不提供 tdsql 服务 |
| NoServiceAvailableForThisZoneId | 请求的 zoneId 不提供tdsql服务 |
| ReachThememSizeLimit | 申请的 tdsql 超过最大/最小容量限制 |
| ReachTheAmountLimit | 申请的 tdsql 数量超过最大/最小购买数限制 |
| InstanceNameIllegal | 更改实例名提供的实例名不合法 |
| EmptyPasswordForbidden | 不能使用空密码 |
| OldPasswordNotCorrect | 重置密码时，原密码不符合 |
| InstanceExpired | tdsql 实例已经过期，需要续期 |
| NoSpecFound | 找不到对应spec的title |
| NoInstanceFound | 实例不存在 |
| InstanceStatusAbnormal | 实例状态异常(非删除), 不能进行操作 |
| SameSpecId | 扩容时指定的specid和实例的specid一样 |
| SpecIdIllegal | 扩容时指定的specid非法, 不在spec列表中 |
| EmptyIP | 更改接入机ip时，接入机ip为空 |
| UserNotInTheWhiteList | 用户不在白名单中 |
| SuperUserForbidden | 不允许操作超级用户tdsql |
| DbNameIllegal | 数据库名称不合法 |
| UserHostExistsAlready | 用户已经存在 |
| UserHostDoesNotExist | 用户不存在 |
| InstanceAlreadyDeleted | 实例已删除 |
| IllegalLogSaveDays | 修改log保存天数时过小或过大 |
| IllegalTime | 错误的时间参数 |
| RepeatOrderNumber | 实例申请订单号重复提交 |
| IllegalInstanceId | 错误的实例ID |
| LogNotExisted | 日志缺失 |
| IllegalInitParam | 初始化实例参数非法 |
| SyncTaskDeleted | 同步任务已经删除 |
| SyncTaskParamIllegal | 同步任务参数非法 |
| IllegalDeadline | Deadline时间错误 |
| RuleAbnormal | 策略状态非法 |
| AuditServiceAlreadyOn | 审计服务重复开通 |
| RuleNameExisted | 规则名称已经存在 |
| RuleStatusError | 规则状态错误 |
| RuleParamsError | 规则参数错误 |
| StrategyNameExists | 策略名称存在 |
| SessionIdExpired | 会话Id过期 |
| PriorityIDError | PriorityID不一致 |
| RulesNotExist | 规则不存在 |
| StrategyNotExist | 策略名称不存在 |
| ConnectMongodFailed | 连接mongod失败 |
| RulesExisted | 规则关联的策略存在 |
| CharacterError | 错误的字符 |
| SyncDbFailed | 同步实例db错误 |
| TableInfoNotCorrect | 多源同步表数据库时，目的库与源库表信息不一致 |
| SrcTableErrorOrNotExist | 源表错误or不存在 |
| DstTableErrorOrNotExist | 目的表错误or不存在 |
| ShardNotExist | 分片不存在 |
| AuditServiceAbnormal | 审计服务状态非法 |
| FlowStatusError | 流程错误 |
| RedoFlowFailed | 重启流程失败 |
| InstanceHasBeenLocked | tdsql已经被其它流程锁定 |
| DbOperationFailed | DB内部失败 |
| OssOpertaionFailed | OSS内部失败 |
| CreateUserFailed | 创建用户失败 |
| GetUserListFailed | 获取用户列表失败 |
| CopyRightError | 复制权限错误 |
| DeleteUserFailed | 删除用户失败 |
| GetRightFailed | 获取权限失败 |
| GetTableInfoFailed | 获取表结构失败 |
| GetDbconfigFailed | 获取参数失败 |
| GetDbListFailed | 获取数据库列表失败 |
| GetDbObjectFailed | 获取数据库对象失败 |
| GetSpecInfoFailed | 获取规格信息失败 |
| ResetPasswordFailed | 重置密码失败 |
| ModifyRightFailed | 修改权限失败 |
| GetInstanceInfoFailed | 获取实例信息失败 |
| StopMigrateTaskFailed | 停止迁移任务 |
| MigrateStartFailed | 开始迁移db错误 |
| CheckDbInfoFailed | 检查数据库错误 |
| CheckMigrateInfoFailed | 检查迁移信息错误 |
| GetMigrateDbListFailed | 获取迁移库列表错误 |
| GetMigrateObjectListFailed | 获取迁移对象列表错误 |
| FinishMigrateTaskFailed | 完成迁移任务错误 |
| QueryMigrateResultFailed | 查询校验迁移任务结果失败 |
| BadUserType | 错误的用户类型 |
| BadUserRight | 错误的用户权限 |
| CDBError | CDB接口失败 |
| CDBMasterError | CDB MASTER失败 |
| CNSAuthFailed | CNS鉴权失败 |
| CNSNSFailed | CNS NS错误 |
| VPCError | VPC错误 |
| BaradError | Barad错误 |
| JsonUnmarshaFailed | json 解析错误 |
| NoDataFetched | 未拉取到数据 |
| ReadDataFailed | 读取返回数据错误 |
| BadRequest | 发起请求错误 |
| MakeRequestFailed | 拼接请求时发生错误 |
| HDFSError | HDFS错误 |
| MigrateTaskLocked | 迁移任务在其他操作中 |
| NoMigrateTask | 没有指定的迁移任务 |
| MigrateTaskDeleted | 迁移任务已经删除 |
| MigrateTaskAlreadyRunning | 迁移任务正在运行中 |
| MigrateTaskAlreadySuccess | 迁移任务已经成功 |
| MigrateTaskNotTunning | 迁移任务不再运行中 |
| MigrateTaskParamError | 迁移任务参数错误 |
| MigrateTaskNoCdbInstance | 没有对应的CDB实例 |
| OssTaskStatusNotOk | 迁移任务oss任务状态没ok |
| MigrateTaskNoCvmInstance | 没有对应的cvm实例 |
| VpcMigrateNotSupport | vpc迁移不支持 |
| CvmIpNotCorrect | cvm ip不对 |
| MigrateTaskCheckFailed | 迁移任务校验失败, 不能启动 |
| MigratTaskUnchecked | 迁移任务未校验, 不能启动 |
| MigrateCheckIdInvalid | 迁移任务校验任务id无效 |
| DfwError | DFW接口错误 |
| CDBOSSFailed | CDB OSS错误 |
| LogDBFailed | logDB接口错误 |
| TgwApplyRuleFailed | TGW规则应用错误 |
| TGWOpRsFailed | TGW操作实体机失败 |
| TGWAddGslbFailed | TGW添加GSLB失败 |
| TGWDeleteGslbFailed | TGW删除GSLB失败 |
| InnerSystemError | 内部系统错误，和业务无关 |
| ConfigFileFormatErrorEgIntStringBooLTypeError | 配置文件内容格式错误 |
| NotSupportNow | 暂时不支持按量计费功能 |
| BalanceIsNotEnough | 余额不足 |
| ReachTheAmounLimit | 购买数量超过限制 |
| ParamError | 逻辑参数错误 |
| RegionUnavailable | 该区域无此服务 |

