
# Radix API Framework
----------------------------------------------
##Test Scenarios

Note:

API 1=`GET http://localhost:8080/hashes`

API 2=`GET http://localhost:8080/piece/:hashId/:pieceIndex`

N =Total count of pieces


1.Verify that User receiving merkel root and total count of pieces in API 1 call.

2.Verify that contest and proof are received in response after caliing API 2 with merkle hash root and piece index.

3.Verify that http request gives 200 status when user gives peiceindex as Total count of pieces(N)-1.

4.Verify that http request gives 404 status when user gives peiceindex as Total count of pieces(N).

5.Verify that sibling hash in proof is padded with 0 when http request for API 2 is made for last index and total count of pieces are odd.

6.Verify that merkle hash can be reconstructed from received  proof and matches with merkel root hash if same file is received from trustless server.

7.Verify that response header contains content type as 'charset=utf-8' and transfer-Encoding as 'Chunked'.

8.Verify that server 'merkle-tree-java.jar'works for all type of files and total number of pieces value equal to file size divided by 1kb.

9.Verify that elements(count) of proof in response gets change as file size changed.



*Scenarios 3 and 4 can be automated by reusing step defination for status check and creating new generic step defination to pass piece index as per scenario as per pieces count .

*Scenario 5 can be automated by wrting step defination to verify sibling hash in proof is padded with 0 for 1st element in proof array.

*Scenario 6 can be automated by adding proof starting with sibling leaf node hash and continuing with uncle hash untill we get merkel hash root.And finally checking with merkel hash root from trusted server.

*Scenario 7,8&9 can be automated by creating respective step defination for scenario validation.
