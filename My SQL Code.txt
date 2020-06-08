CREATE SCHEMA `pharmacy` ;

****************************************************

CREATE TABLE `pharmacy`.`customer` (
  `Customer_id` INT NOT NULL,
  `Customer_fn` VARCHAR(50) NOT NULL,
  `Customer_ln` VARCHAR(50) NOT NULL,
  `Email_id` VARCHAR(50) NOT NULL,
  `Contact_no` VARCHAR(10) NOT NULL,
  `Gender` ENUM("m", "f") NOT NULL,
  PRIMARY KEY (`Customer_id`));

****************************************************

INSERT INTO customer (Customer_id,Customer_fn,Customer_ln,Gender,Email_id,Contact_no)

VALUES
    (1001,'Kristian','Riley','m','k.riley@gmail.com',9387590958),
    (1002,'Leonardo','Andrews','m','l.andrews@gmail.com',9897543123),
    (1003,'John','Myers','m','j.myers@yahoo.com',9689402634),
    (1004,'Edith','Phillips','f','e.phillips@yahoo.com',9948384305),
    (1005,'Brianna','Alexander','f','b.alexander@yahoo.com',9976296499),
    (1006,'Vanessa','Robinson','f','v.robinson@gmail.com',9074230937),
    (1007,'Patrick','Walker','m','p.walker@gmail.com',9584044972),
    (1008,'Carl','Armstrong','m','c.armstrong@yahoo.com',9473999261),
    (1009,'Lucas','Stevens','m','l.stevens@gmail.com',9936172829),
    (1010,'Adam','Armstrong','m','a.armstrong@yahoo.com',9709376725),
    (1011,'Anna','Thompson','f','a.thompson@gmail.com',9816063884),
    (1012,'Lilianna','Smith','f','l.smith@yahoo.com',9201461338),
    (1013,'Sam','Brown','m','s.brown@gmail.com',9934751178),
    (1014,'Michelle','Barnes','f','m.barnes@gmail.com',9784399417),
    (1015,'Adelaide','Campbell','f','a.campbell@yahoo.com',9837161513);

*************************************************************


CREATE TABLE `pharmacy`.`hospital` (
  `Hospital_id` INT NOT NULL,
  `Hospital_name` VARCHAR(80) NOT NULL,
  `R_name` VARCHAR(45) NOT NULL,
  `R_id` INT NOT NULL,
  `Email_id` VARCHAR(45) NOT NULL,
  `Contact_no` VARCHAR(10) NOT NULL,
  `Gender` ENUM("m", "f") NOT NULL,
  PRIMARY KEY (`Hospital_id`));


*****************************************************************

INSERT INTO hospital (Hospital_id,R_name,Gender,Email_id,Contact_no,Hospital_name,R_id)
VALUES
    (3001,'Fenton Myers','m','mgh@gmail.com',9843199944,'Massachusetts General Hospital',26808),
    (3002,'Deanna Murphy','f','hopkins@yahoo.com',9433074950,'Johns Hopkins Hospital',41453),
    (3003,'Lenny Higgins','m','clevelandgh@yahoo.com',9071381907,'Cleveland General Hospital',65538),
    (3004,'Alisa Walker','f','nyp@gmail.com',9273539452,'NY Presbyterian Hospital',51005),
    (3005,'Mike Wilson','m','ucla@gmail.com',9873611739,'UCLA Medical Center',17612),
    (3006,'Joyce Clark','f','ucsf@yahoo.com',9703653085,'UCSF Medical Center',38350),
    (3007,'Oscar Elliott','m','sinai@yahoo.com',9105547422,'Cedars-Sinai Medical Center',17478),
    (3008,'Charlotte Armstrong','f','c.armstrong@yahoo.com',9880725491,'NYU Langone Hospital',49985),
    (3009,'Harold Johnston','m','nwh@gmail.com',9065263761,'Northwestern Memorial Hospital',37917),
    (3010,'Lenny Edwards','m','stanfordhc@yahoo.com',9139548568,'Stanford Health Care',10967),
    (3011,'Chloe Robinson','f','brigham@gmail.com',9577391988,'Brigham and Womens Hospital',71060),
    (3012,'Grace Wright','f','mountsinai@gmail.com',9021825696,'Mount Sinai Hospital',78493),
    (3013,'Lily Armstrong','f','upmcside@gmail.com',9523897634,'UPMC Presbyterian Shadyside Hospital',73961),
    (3014,'Adele Robinson','f','keckhos@yahoo.com',9599171588,'Keck Hospital',61316),
    (3015,'Tara Cunningham','f','t.cunningham@yahoo.com',9120044849,'Houston Methodist Hospital',11178);


***************************************************************************


INSERT INTO customer (Customer_id,Customer_fn,Customer_ln,Gender,Email_id,Contact_no)

VALUES
    (1016,'Lyndon','Roberts','m','l.roberts@gmail.com',9114846090),
    (1017,'Dale','Campbell','m','d.campbell@yahoo.com',9122896418),
    (1018,'Vincent','Turner','m','v.turner@gmail.com',9856307999),
    (1019,'Carl','Stevens','m','c.stevens@gmail.com',9385852284),
    (1020,'Miley','Spencer','f','m.spencer@yahoo.com',9645680082);


******************************************************************************


INSERT INTO hospital (Hospital_id,R_name,Gender,Email_id,Contact_no,Hospital_name,R_id)
VALUES
    (3016,'Chelsea Douglas','f','tufts@gmail.com',9289066297,'Tufts Medical Center',32751),
    (3017,'Amelia Rogers','f','beaumont@gmail.com',9146144614,'Beaumont Hospital',57955),
    (3018,'Sofia Howard','f','mvhos@yahoo.com',9116113993,'Miami Valley Hospital',21951),
    (3019,'Aiden Holmes','m','ialexhos@yahoo.com',9088738973,'Inova Alexandria Hospital',98260),
    (3020,'Rubie Foster','f','fordhos@yahoo.com',9319106838,'Henry Ford Hospital',54660);



*******************************************************************************


CREATE TABLE `pharmacy`.`medicine` (
  `Medicine_id` VARCHAR(10) NOT NULL,
  `M_name` VARCHAR(80) NOT NULL,
  `Manu_name` VARCHAR(80) NOT NULL ,
  `Type` VARCHAR(45) NOT NULL,
  `Self_loc` VARCHAR(20) NOT NULL,
  `Price` INT NOT NULL,
  PRIMARY KEY (`Medicine_id`));


*****************************************************************************


CREATE TABLE `pharmacy`.`surgical_products` (
  `SP_id` VARCHAR(10) NOT NULL,
  `S_name` VARCHAR(80) NOT NULL,
  `Man_name` VARCHAR(80) NOT NULL ,
  `Self_loca` VARCHAR(20) NOT NULL,
  `Price` INT NOT NULL,
  PRIMARY KEY (`SP_id`));


*****************************************************************************


CREATE TABLE `pharmacy`.`ayurvedic_med` (
  `AM_id` VARCHAR(10) NOT NULL,
  `AM_name` VARCHAR(80) NOT NULL,
  `Man_name` VARCHAR(80) NOT NULL,
  `Type` VARCHAR(45) NOT NULL,
  `Self_loc` VARCHAR(20) NOT NULL,
  `Price` INT NOT NULL,
  PRIMARY KEY (`AM_id`));


*********************************************************************************


CREATE TABLE `pharmacy`.`general_items` (
  `GItem_id` VARCHAR(10) NOT NULL,
  `GItem_name` VARCHAR(80) NOT NULL,
  `Manu_name` VARCHAR(80) NOT NULL ,
  `Self_loc` VARCHAR(20) NOT NULL,
  `Price` INT NOT NULL,
  PRIMARY KEY (`GItem_id`));


*****************************************************************************

CREATE TABLE `pharmacy`.`inventory` (
  `ID` VARCHAR(10) NOT NULL,
  `Available` INT NOT NULL,
  `Sold` INT NOT NULL,
  `Exp_date` DATE NOT NULL,
  PRIMARY KEY (`ID`));

**************************************************************************


ALTER TABLE `pharmacy`.`inventory` 
ADD CONSTRAINT `ID1`
  FOREIGN KEY (`ID`)
  REFERENCES `pharmacy`.`ayurvedic_med` (`AM_id`)
  ON DELETE CASCADE
  ON UPDATE CASCADE,
ADD CONSTRAINT `ID2`
  FOREIGN KEY (`ID`)
  REFERENCES `pharmacy`.`general_items` (`GItem_id`)
  ON DELETE CASCADE
  ON UPDATE CASCADE,
ADD CONSTRAINT `ID3`
  FOREIGN KEY (`ID`)
  REFERENCES `pharmacy`.`medicine` (`Medicine_id`)
  ON DELETE CASCADE
  ON UPDATE CASCADE,
ADD CONSTRAINT `ID4`
  FOREIGN KEY (`ID`)
  REFERENCES `pharmacy`.`surgical_products` (`SP_id`)
  ON DELETE CASCADE
  ON UPDATE CASCADE;



*********************************************************************


INSERT INTO ayurvedic_med(AM_id,AM_name,Man_name,Type,Self_loc,Price)
VALUES
	('A001','Sudarshan Ghanvati','ZANDU PHARMACEUTICALS WORKS LTD.','Tablet','AS1',80),
	('A002','Zandu Balm 25 ml','ZANDU PHARMACEUTICALS WORKS LTD.','Gel','AZ1',85),
	('A003','Sitopaladi Churna 25g','ZANDU PHARMACEUTICALS WORKS LTD.','Tablet','AS1',40),
	('A004','Drakshasava 450 ml','ZANDU PHARMACEUTICALS WORKS LTD.','Syrup','AD1',175),
	('A005','Pudin Hara Active 10 ml','Dabur India Ltd.','Syrup','AP1',20),
	('A006','Pudin Hara Pearls','Dabur India Ltd.','Tablet','AP1',20),
	('A007','Honitus Cough Syrup','Dabur India Ltd.','Syrup','AH1',65),
	('A008','Himcolin Gel','The Himalaya Drug Company','Gel','AH1',160);

****************************************************************************

INSERT INTO medicine(Medicine_id,M_name,Manu_name,Type,Self_loc,Price)
VALUES
	('M001','Cetimax Cold Tablet','ZYDUS CADILA','Tablet','MC1',25),
	('M002','Cold Nova','UNIVERSAL HEALTH SCIENCES','Tablet','MC1',38),
	('M003','Calpol 500mg','GLAXOSMITHKLINE PHARMACEUTICALS Ltd','Tablet','MG1',15),
	('M004','LEMOLATE ','YASH PHARMA LABORATORIES Pvt Ltd','Tablet','ML1',30),
	('M005','Cough Cure Expectorant 500 ml','Hapro Homeo-Chem (P) Ltd.','Syrup','MC1',255);

**********************************************************************

INSERT INTO surgical_products(SP_id,S_name,Man_name,Self_loca,Price)
VALUES
	('S001','Sponge Holding & Dressing Forceps,Foerster,20Cm-8"','Hebson Surgical Company','SF1',350),
	('S002','Scissors,Olivecrona,14.5Cm-5 3/4"','Hebson Surgical Company','SO1',550),
	('S003','METZENBAUM -STILLIES - SCISSOR 4"','Warden Surgical CO. PVT. LTD.','SM1',400);

******************************************************************************

INSERT INTO general_items(GItem_id,GItem_name,Manu_name,Self_loc,Price)
VALUES
	('G001','Dabur Glucose D','Dabur India Ltd.','GG1',45),
	('G002','Dabur Honey','Dabur India Ltd.','GH1',180),
	('G003','Potato Wafers- Classic Salted','Balaji Wafers and Namkeens Pvt. Ltd.','GB1',15),
	('G004','Fogg Impressio','Vini Cosmetics Pvt. Ltd','GB1',175),
	('G005','Potato Wafers- Cream N Onion','Balaji Wafers and Namkeens Pvt. Ltd.','GB1',15

**********************************************************************************

DROP TABLE `pharmacy`.`inventory`;

*****************************************

CREATE TABLE `pharmacy`.`inventory` (
  `ID` VARCHAR(10) NOT NULL,
  `Available` INT NOT NULL,
  `Sold` INT NOT NULL,
  `Exp_date` DATE NOT NULL,
  PRIMARY KEY (`ID`));

************************************************

INSERT INTO inventory (ID,Available,Sold,Exp_date)
VALUES
	('A001',15,5,'2020-11-01'),
	('A002',10,3,'2021-02-19'),
	('A003',8,5,'2021-07-12'),
	('A004',10,4,'2022-01-28'),
	('A005',12,8,'2020-09-22'),
	('A006',10,5,'2020-10-19'),
	('A007',8,2,'2021-04-03'),
	('A008',5,1,'2022-01-01'),
	('M001',15,8,'2021-01-01'),
	('M002',10,5,'2021-05-16'),
	('M003',20,12,'2021-12-31'),
	('M004',10,4,'2021-11-16'),
	('M005',10,3,'2022-02-25'),
	('S001',5,2,'2032-07-17'),
	('S002',5,1,'2035-01-15'),
	('S003',8,3,'2029-08-12'),
	('G001',12,5,'2021-06-19'),
	('G002',8,2,'2045-09-29'),
	('G003',18,12,'2021-01-01'),
	('G004',10,4,'2022-12-01'),
	('G005',20,10,'2021-01-01'),
	('G006',12,6,'2021-06-30'),
	('G007',10,5,'2022-05-23');

************************************************

ALTER TABLE `pharmacy`.`medicine` 
ADD COLUMN `Prescription` ENUM("Y", "N") NOT NULL AFTER `Price`;

*****************************************************

UPDATE `pharmacy`.`medicine` SET `Prescription` = 'N' WHERE (`Medicine_id` = 'M001');
UPDATE `pharmacy`.`medicine` SET `Prescription` = 'N' WHERE (`Medicine_id` = 'M004');
UPDATE `pharmacy`.`medicine` SET `Prescription` = 'N' WHERE (`Medicine_id` = 'M003');



********************************************

CREATE TABLE `pharmacy`.`prescription_details` (
  `Pres_no` VARCHAR(10) NOT NULL,
  `Doc_regno` VARCHAR(20) NOT NULL,
  `Doc_name` VARCHAR(45) NOT NULL,
  `Doc_address` VARCHAR(100) NOT NULL,
  `Status` VARCHAR(45) NOT NULL,
  PRIMARY KEY (`Pres_no`));

**************************************

CREATE TABLE `pharmacy`.`payment` (
  `Pay_id` VARCHAR(10) NOT NULL,
  `Mode` VARCHAR(45) NOT NULL,
  `Amount` FLOAT NOT NULL,
  PRIMARY KEY (`Pay_id`));

**************************************

ALTER TABLE `pharmacy`.`prescription_details` 
CHANGE COLUMN `Status` `Medicine` VARCHAR(45) NOT NULL ;

**************************************

ALTER TABLE `pharmacy`.`prescription_details` 
ADD COLUMN `Customer_id` VARCHAR(10) NOT NULL AFTER `Medicine`;

**************************************

INSERT INTO medicine(Medicine_id,M_name,Manu_name,Type,Self_loc,Price,Prescription)
VALUES
('M006','Malidens 500Mg','Endocard India pvt limited','Tablet','MC2',35,'Y'),
('M007','Hindrishiayurveda Zero-tar Syrup ','Endocard India pvt Limited','Syrup','MC3',30,'N'),
('M008','Electral Powder','Koye Pharmaceuticals Pvt ltd','Power','MC7',20,'N'),
('M009','Ascabiol Emulsion','Abbott','Syrup','MC5',35,'Y'),
('M010','Durajoint Plus Capsule','Methylphenidate','Tablet','MC4',45,'N'),
('M011','Knight Power','Universal Heth science','Power','MC7',35,'Y'),
('M0012','Derantox Capsule','Koye Pharmaceuticals Pvt ltd','Tablet','MC9',22,'Y'),
('M013','Goestress Capsule','Koye Pharmaceuticals Pvt ltd','Tablet','MC3',40,'Y'),
('M014','Endolac-Fort Capsule','ZYDUS CADILA','Tablet','MC8',65,'N'),
('M015','Becotrol Capsules','ZYDUS CADILA','Tablet','MC9',70,'N');

**************************************

INSERT INTO surgical_products(SP_id,S_name,Man_name,Self_loca,Price)
VALUES
(S005, Catheter Trays, All India Surgical Manufacturing Company, SF4, 300),
(S006, Electrosurgical Dispersive Plates, Bharat Surgical Company, SF6, 250),
(S007, Head Mirror Reflectors, DOLPHIN INSTRUMENTS Company, SF7, 340),
(S008, Instrument Holders, MEHTA TRADING CORPORATION, SF5, 500),
(S009, Instrument Stands Stainless Steel, Siddhi Surgical, SF3, 300),
(S010, Lubricating Gel, Parmar SurgicalsCompany, SF1, 600),
(S011, Patient positioners, Kalelker Surgicals Pvt Ltd, SF8, 350),
(S012, Skin cream, Navkar Medical Supply, SF2, 3250),
(S013, Gloves, Hebson Surgical Company, SF4, 450),
(S014, CSR Wraps, Bafna Surgical Company, SF4, 150),
(S015, Face Mask, Manufacturing of E.N.T Instruments, SF9, 360);

**************************************

INSERT INTO customer (Customer_id,Customer_fn,Customer_ln,Gender,Email_id,Contact_no)
VALUES
(1027,'Ravi',' Kishor','m','ravi.k@gmail.com', 9876378290),
(1028,'Mehak','Mittal','f','mmittal@gmail.com',9769022092),
(1029,'Ananya','Pathak','f','ananyap@gmail.com',9762510096),
(1030,'Atharva','Pawar','m','atharvapawar@gmail.com',9672614627),
(1031,'Harshal','Jain','m','harshal200@gmail.com',9920449752),
(1021,'Rishika','Sharma','f','rishika3031@gmail.com',9172615278),
(1022,'Namitha','Menon','f','namitha.m20@gmail.com',9800067543),
(1023,'Dhruv','Bansal','m','dhruvbansal@gmail.com',9876786908),
(1024,'Erika','D Souza','f','erika202@gmail.com',8262882727),
(1025,'Khushboo','Kumar','f','kkumar@gmail.com',8867562154),
(1026,'Chirag','Pinto','m','chirag44@gmail.com',9890976589);

**************************************

INSERT INTO hospital (Hospital_id,R_name,Gender,Email_id,Contact_no,Hospital_name,R_id)
VALUES

(3027,'Rekha Sagar','f','rekha.s@gmail.com',9878767809,'MGM Hospital',26809),
(3031,'Vinod Kumar','m','vinodk@gmail.com',9878777009,'Fortis Hospital',26810),
(3028,'Kiran  Kaur','f','kaur @gmail.com',8890567809,'VML Hospital',26811),
(3029,'Rahul sahu','m','rahul.s@gmail.com',9878767809,'MGM Hospital',26812),
(3030,'Pallavi Patil','f','contactus@fortis.com',9878756789,'Fortis Hospital',26813),
(3021,'Om Sharma','m','contactus@apollo.com',9884767809,'Apollo Hospital',26814),
(3022,'Kunal Mittal','m','contactus@apollo.com',988476009,'Apollo Hospital',26815),
(3023,'Sanjana Sanil','f','contactus@mgm.com',9884767809,'MGM Hospital',26816),
(3024,'Charu Sharma ','m','contactus@pkc.com',8890765478,'PKCHospital',26817),
(3025,'Dev Aras','m','contactus@cloudnine.com',9884767809,'Cloud9 Hospital',26818),
(3026,'Vikram Jain','m','contactus@uma.com',9884767809,'Uma Hospital',26819);

**************************************

INSERT INTO ayurvedic_med(AM_id,AM_name,Man_name,Type,Self_loc,Price)
VALUES
('A009','Jiva stress free','North India  Life Science','Tablet','AS2',80),
('A010','Indukantham','North India life Science','Tablet','AS3',100),
('A011','Yogi Kantika Pills','North India  Life Science','Tablet','AS4',110),
('A012','Organic Shatavari Root','Paras Ayurvedic Pharma','Power','AS5',70),
('A014','Soria Natual','Paras Ayurvedic Pharma','Syrup','AS5',200),
('A016','Kama Ayurvedic Oil','Immense Healthcare','Oil','AS7',210),
('A017','Sambucol For Kids','Immense Healthcare','Tablet','AS8',100),
('A018','Himaliya Brahmi','The Himalaya Drug Company','Oil','AS6',90);

**************************************

INSERT INTO general_items(GItem_id,GItem_name,Manu_name,Self_loc,Price)
VALUES
('G008', 'KitKat Chocolate', 'Nestle India Ltd', 'GG2', '100'),
('G009', 'Orange Khari biscuit', 'Parampara India Ltd', 'GG3', '90'),
('G010', 'Maggi', 'Nestle India Ltd', 'GG5', '200'),
('G011', 'Snickers Bar', 'Mars Pvt Ltd', 'GG7', '30'),
('G012', 'Butter Milk Packed', 'Nestle India Ltd', 'GG6', '205'),
('G013', 'Lays chips', 'Lays chips pvt Ltd.', 'GG6', '300'),
('G014', 'Ice Cream Stick', 'Dairy Queen pvt Ltd', 'GG5', '100'),
('G015', 'Pepper Soda', 'Paper boat India pvt Ltd.', 'GG7', '200');

**************************************

INSERT INTO inventory (ID,Available,Sold,Exp_date)
VALUES
	('A009',20,7,'2020-12-01'),
	('A010',35,10,'2023-12-01'),
	('A011',50,20,'2021-8-01'),
	('A012',100,20,'2022-6-10'),
	('A013',35,7,'2020-07-25'), 
	('A014',50,15,'2023-06-20'),
	('A015',25,7,'2020-11-11'),
	('A016', 60,30,'2021-7-05'),
	('A017',70,20,'2020-2-01'),
	('A018',80,30,'2021-12-11'),
	('M006',20,7,'2020-12-01'),
	('M007',25,5,'2023-12-01'),
	('M008',50,10,'2010-11-21'),
	('M009',50,20,'2022-8-10'),
	('M010',10,5,'2021-1-01'),
	('M011',30,10,'2023-5-01'),
	('M012',50,8,'2020-12-30'),
	('M013',40,7,'2021-9-01'),
	('M014',50,10,'2022-11-11'),
	('M015',60,10,'2020-12-01'),
	('G008',50,10,'2010-11-21'),
	('G009',50,20,'2022-8-10'),
	('G010',10,5,'2021-1-01'),
	('G011',30,10,'2023-5-01'),
	('G012',50,8,'2020-12-30'),
	('G013',40,7,'2021-9-01'),
	('G014',50,10,'2022-11-11'),
	('G015',60,10,'2020-12-01'),
	('S004',25,10,'2020-08-01'),
	('S005',20,5,'2023-10-01'),
	('S006',20,7,'2020-12-01'),
	('S007',25,5,'2023-12-01'),
	('S008',50,10,'2010-11-21'),
	('S009',100,20,'2022-8-10'),
	('S010',150,60,'2021-1-01'),	
	('S011',300,150,'2023-5-01'),
	('S012',50,8,'2020-12-30'),
	('S013',100,7,'2021-9-01'),
	('S014',200,90,'2022-11-11'),
	('S015',60,10,'2020-12-01');

**************************************

INSERT INTO medicine(Medicine_id,M_name,Manu_name,Type,Self_loc,Price)
VALUES
('PM001','Metronidazole', 'Bravecto Productions','Tablet', 'PMD7', 400),
('PM002','Famotidine', 'Bravecto productions','Tablet', 'PMA4', 300),
('PM003','Diphenhydramine', 'Vivapets company','Tablet', 'PMC6', 500),
('PM004','Enacard', 'Viva pets company','Tablet', 'PME7', 600),
('PM005','Salix', 'Cosequin production','Syrup', 'PMB2', 250),
('PM006','Rimadyl', 'Cosequin production', 'Tablet','PMD8', 450),
('PM007','Atopica', 'Milbemax company', 'Tablet','PMA5', 350),
('HP001','Pulsatilla', 'HomyoXpert company', 'Tablet','HPE6', 85),
('HP002','Nux vomica', 'HomyoXpert company', 'Tablet','HPB3', 80),
('HP003','Magnesia phosphorica', 'Homeodent company', 'Tablet','HPC8', 90),
('HP004','Ignatia', 'Homeodent company', 'Tablet','HPD1', 100),
('HP005','Allium cepa', 'Boiron Homeopathics', 'Tablet','HPC7', 200),
('HP006','Chamomilla', ' BHI Homeopathics', 'Tablet','HPC6', 250),
('HP007','Hypericum', 'Hevert Pharmaceuticals','Tablet', 'HPA5', 300);

**************************************

INSERT INTO care(C_id,CP_name,Manu_name,Self_loc,Price)
VALUES
('SC001',''AGE REVOLUTION NIGHT CREAM, 'NeuMe productions', 'SCD7', 400),
('SC002','Charcoal Facewash', 'NeuMe productions', 'SCF5', 300),
('SC003','Hello Aloe! Soothing Skincare Kit', 'The body shop productions', 'SCE6', 500),
('SC004','Seaweed Balance Sheet Mask', 'Body Shop', 'SCA2',200),
('SC005',''Lip Sleeping Mask, 'Sephora Productions', 'SCB8',350),
('SC006','The True Cream Aqua Bomb', 'Sephora Productions', 'SCB4',450),
('SC007','Skin Defence Multi-Protection Face Mist', 'Sephora Productions', 'SCC6',550),
('HH001','Juicy Pear Body Butter', 'Body Shop', 'HHD7', 400),
('HH002','White Musk Flora Body Lotion', 'Body Shop', 'HHA3', 300),
('HH003','Shower gel', 'Coco Soul Production', 'HHE6', 200),
('HH004','Exotic rose air freshener', 'Winall production', 'HHB6', 350),
('HH005','Colgate charcoal clean toothpaste ', 'Colgate productions ', 'HHC8', 450),
('HH006','Dettol Liquid hand sanitizers', 'Dettol pvt limited', 'HHD2', 200),
('HH007','Dettol Instent Hand Wash', 'Dettol pvt limited', 'HHA1', 300);

**************************************

INSERT INTO inventory (ID,Available,Sold,Exp_date)
VALUES
('SC001',10,5,'2022-05-23'),
('SC002',20,5,'2021-05-26'),
('SC003',30,15,'2022-08-13'),
('SC004',15,3,'2022-04-20'),
('SC005',35,10,'2023-01-20'),
('SC006',20,6,'2021-02-15'),
('SC007',11,2,'2022-07-13'),
('HH001',10,5,'2022-05-23'),
('HH002',20,7,'2022-10-20'),
('HH003',30,10,'2021-05-13'),
('HH004',40,15,'2023-12-01'),
('HH005',50,20,'2022-06-20'),
('HH006',55,25,'2021-03-26'),
('HH007',40,15,'2022-07-28'),
('PM001',35,6,'2021-07-15'),
('PM002',50,5,'2022-05-20'),
('PM003',11,5,'2022-03-13'),
('PM004',17,4,'2022-09-21'),
('PM005',45,10,'2023-08-31'),
('PM006',10,5,'2022-05-23'),
('PM007',15,3,'2021-07-15'),
('HP001',10,5,'2022-05-23'),
('HP002',20,7,'2022-10-20'),
('HP003',30,10,'2021-05-13'),
('HP004',40,15,'2023-12-01'),
('HP005',50,20,'2022-06-20'),
('HP006',55,25,'2021-03-26'),
('HP007',40,15,'2022-07-28');

******************************

CREATE TABLE `pharmacy`.`add_to_cart` (
  `User_id` VARCHAR(10) NOT NULL,
  `Item_id` VARCHAR(45) NOT NULL,
  `Price` INT NOT NULL,
  PRIMARY KEY (`User_id`));

****************************

CREATE TABLE `pharmacy`.`payment` (
  `Pay_id` VARCHAR(10) NOT NULL,
  `Mode` VARCHAR(45) NOT NULL,
  `Amount` FLOAT NOT NULL,
  PRIMARY KEY (`Pay_id`));
