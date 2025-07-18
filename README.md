# CD
Level 1:

recv call in	
- fail before translation process (status != '10001f' and status != '10001e' and LENGTH(status) < 8 and status != '0')
- after translation process 
	- cld_ACM > 0 / = 0 
		- Translated / Not Translated (status = '10001f')


need to break down further by country / categories A,b,c after one lump sum summary?

 Level 2:
 
 build the above in table form, by adding below category A,B,C as first column, and regex proposal as last
	CASE 
		WHEN regexp_like(cld_num, '^(?:0(11)\\d{8}|01[(02-9)]\\d{7}|03\\d{8}|0([4-9])\\d{7})$') = TRUE THEN 1 -- domestic malaysian number 
		WHEN regexp_like(cld_num, '^(?:\\+?60)(?:(11)\\d{8}|1[(02-9)]\\d{7}|3\\d{8}|[(4-9)]\\d{7})$') = TRUE THEN 2 -- international malaysian number 
		-- WHEN cat B 
		ELSE 9 
	END AS num_sub_cat



 Level 3:
 
 Detailed CDR of the above selected category..
