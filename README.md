# k99
new little repository.
try change a new branch file.
update 2nd.



SELECT acc.a '财务账',acc.b '明细账', acc.c '减法', acc.d 'code', COUNT(acc.d) from (SELECT SUM(fc.CHARGE) a, sdd.feeAll b, SUM(fc.CHARGE)-sdd.feeAll c , fc.STU_CODE d FROM fee_charge fc LEFT JOIN (
SELECT SUM(sd.fee_money) feeAll, sd.stu_code stuCode FROM stufee_detail sd GROUP BY sd.stu_code)sdd ON fc.STU_CODE=sdd.stuCode GROUP BY fc.STU_CODE )acc GROUP BY acc.c;

SELECT SUM(fc.CHARGE) a, sdd.feeAll b, SUM(fc.CHARGE)-sdd.feeAll c , sc.creditsum '贷款', dd.sum '缓交', fc.STU_CODE d FROM fee_charge fc LEFT JOIN (
SELECT SUM(sd.fee_money) feeAll, sd.stu_code stuCode FROM stufee_detail sd GROUP BY sd.stu_code)sdd ON fc.STU_CODE=sdd.stuCode 
		LEFT JOIN stu_credit sc ON sc.stu_code=fc.STU_CODE 
		LEFT JOIN stu_delayfee dd ON dd.stu_code=fc.STU_CODE GROUP BY fc.STU_CODE ;

SELECT creditsum FROM stu_credit GROUP BY creditsum;
SELECT * FROM stu_delayfee where sum=3510


end
