# homework0629_Create_DB
 以下為執行指令 
  `` 符號消失，請轉成編寫模式再複製與執行
--------------------------------------------------------------------------------
create database homework default character set utf8;

use homework;


drop table charge;


CREATE TABLE `charge` (
  `id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'id',
  `date` datetime NOT NULL COMMENT '消費日期',
  `buy` int(11) NOT NULL COMMENT '消費金額',
  `items` int(11) NOT NULL COMMENT '項目',
  `receipt` varchar(8) DEFAULT NULL COMMENT '統一發票',
  `note` text COMMENT '備註',
  `creat_date` datetime NOT NULL COMMENT '新增日期',
  `user_id` int(11) NOT NULL COMMENT '使用者',
  `is_enabled` TINYINT(1) NOT NULL DEFAULT '1' COMMENT '是否隱藏',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 AUTO_INCREMENT=1; 



drop table items;

CREATE TABLE `items` (
  `items_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'id',
  `items_list` varchar(10) DEFAULT NULL COMMENT '項目',
  `creat_date` datetime NOT NULL COMMENT '新增日期',
  `user_id` int(11) NOT NULL COMMENT '使用者',
  `is_enabled` TINYINT(1) NOT NULL DEFAULT '1' COMMENT '是否隱藏',
  PRIMARY KEY (`items_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 AUTO_INCREMENT=1;


INSERT INTO `charge` (date,buy,items,receipt,note,user_id) VALUES
('2016/1/1','300','2','12345678','上衣','1'),
('2016/1/1','80','1','87654321','午餐','1'),
('2016/1/2','1000','6','','門票','1'),
('2016/1/2','5000','5','','學費','1');


INSERT INTO `items` (items_list,creat_date,user_id) VALUES
('食',NOW(),'0'),
('衣',NOW(),'0'),
('住',NOW(),'0'),
('行',NOW(),'0'),
('育',NOW(),'0'),
('樂',NOW(),'0');
