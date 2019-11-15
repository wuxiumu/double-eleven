
管理员用户表：

名 | 类型 | 长度 | 小数点 | 不是null
---| ---  | --- | ----- | -----
id	|int	|10	|0	| Y	
username|	varchar	|190|0	| Y 
password	|varchar|	60|	0	|Y
name|	varchar	|255	|0	|  Y
avatar|	varchar	|255|	0	|  	
remember_token|	varchar|	100	|0|  
created_at|	timestamp|	0|	0|	 	 	 
updated_at|	timestamp|	0	|0	|  
 

admin_users.sql
```
SET FOREIGN_KEY_CHECKS=0;

-- ----------------------------
-- Table structure for admin_users
-- ----------------------------
DROP TABLE IF EXISTS `admin_users`;
CREATE TABLE `admin_users` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `username` varchar(190) COLLATE utf8mb4_unicode_ci NOT NULL,
  `password` varchar(60) COLLATE utf8mb4_unicode_ci NOT NULL,
  `name` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `avatar` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `remember_token` varchar(100) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `admin_users_username_unique` (`username`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- ----------------------------
-- Records of admin_users
-- ----------------------------
INSERT INTO `admin_users` VALUES ('1', 'admin', '$2y$10$9R.yk3l/aPMCrH4oUfQ4Q.G74OD3huDK/xrFjzULjHC9eS4mxh3OO', 'Administrator', 'images/20aedc7c13979878323a5681ecd52a39 (1).png', 'SQQpxDkjlHXGn371LsaoOW0QUMGpnJT78O44f5Khsbjy1aHwprzN5GsvJ0Ch', null, '2017-09-12 11:55:49');
INSERT INTO `admin_users` VALUES ('2', '1', '$2y$10$Et26etjCwILO7aooX8V4uehi2fIooHtVODI5Kx0S5EIOymW/zFxXK', '123', 'images/2308797923.jpg', null, '2017-09-04 04:19:27', '2017-09-06 08:18:48');
INSERT INTO `admin_users` VALUES ('3', 'abc', '$2y$10$ZpBYRIUNx3wOBXh/yEifHebo5.ulZNvgHmoCQCUS0fuhPG8wRGlii', 'test abc', null, null, '2017-09-05 11:08:34', '2017-09-05 11:08:34');
INSERT INTO `admin_users` VALUES ('4', 'li', '$2y$10$SbrG4LW/A8uuZyHXx7R7te506TMKyMKS/8ey.rN7.BQzzIzG9/WQO', 'li', null, null, '2017-09-06 07:39:10', '2017-09-06 07:39:10');
INSERT INTO `admin_users` VALUES ('5', 'test1', '$2y$10$68yjRJSd7ZsSHvR21Ik17uMWIrrxX1F/iNmyRt5Ud65RACBycAkVm', 'test1', null, null, '2017-09-07 01:55:20', '2017-09-07 01:55:20');

```