# Quiz questions

This is only a "quiz" in the loosest sense that it's asking questions whose
answers will be part of your grade. Please use *any resources you want*, as
long as you list those resources (e.g. peers, websites, etc.)

## Navigating logs

1. What is the SHA for the last commit made by Prof. Xanda on the branch
xanda_0000_movie_processing?
(For this and future questions, the first 5 characters is plenty - neither
Git nor I need the whole SHA.)
9b257

2. What is the SHA for the last commit associated with line 9 of this file?
68996

3. What did line 12 of this file say in commit d1d83?
I forgot to copy and paste it somewhere, but should be "I should really finish this"

4. What changed between commit e474c and 82045?
for gross_sort, it has been changed from lambda x : x["Gross"] to lambda x : int(x["Gross"])
an top_five from row[:-5:-1] to row[:-6:-1]

## Predicting merges

Assume at the start of each of these three questions that your
branch for switching to a top-10 list was called `top_ten`
and your branch generalizing to any number of movies was called `top_N`.
Predict the behavior of these three possible operations - you don't
have to provide a full `diff` but you should describe at a high level
what changes would happen.

These questions are supposed to be separate paths, not cumulative;
for example, you should *not* assume that the operations of 5 were run
before 6. When testing outcomes later in the lab, you should make sure to
revert back to the state of the branch before you started these questions.

5. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git merge top_N
```
I the top_N branch will merge with the test branch, test branch
will be changed, to included all the updates in top_N

6. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout top_ten
git merge test
```
I guess the test branch will merge with the top_ten branch, top_ten branch
will be changed, to included all the updates in test. So, we change n = 10

7. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git rebase top_ten
git rebase top_N
```
I guess test branch will be changed to include things in top_ten
and top_N, as result we have to change n = 5 to n = 10 in default
to make things compile
