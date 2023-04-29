## 1.Example Execution:				
```
# ./test.sh
# sh test.sh
# bash test.sh
```
## 2.Initialization:			
```
#!/bint/sh
echo "Hello, World!"
```
## 3.Example Command:
|Command|Example|
|:--|:--|
|Comment out|# This is comment.|
|Input new line|echo "Hello,\n World!"|
|Set a variable|[variableName]=[value]|
|Delete a variable|unset [variableName]|
|Use a variable|echo ${[variableName]}|
|Handle variables numerically|echo $((x + y))|
|Include the output of the command in the stirng|echo "Today is $(date)"
||echo "Today is `date`"|

## 4.Default Argument:
|argument|remarks|
|:--|:--|
|$0|ShellScript filename|
|$1|First argument|
|$2|Second argument|
|$#|Number of arguments|

## 5.if:
```
if [ $1 -eq $2 ] ; then
	echo 'equal'
elif [ $1 -ne $2 ] ; then
	echo 'not equal'
else
      echo 'not numetric'
fi
### .\test.sh <variable1> <variable2>
```
## 6.for:
```
for var in a b c
for ((i=0 ; i<10 ; i++))
for i in `seq 10`
do
	echo "test"$i
done
### .\test.sh
```
## 7.relational operator:
|演算子|例|備考|
|:--|:--|:--|
|-eq|test num1 -eq num2|num1 と num2 が等しければ真となる。num1=num2|
|-ne|test num1 -ne num2|num1 と num2 が等しくなければ真となる。num1≠num2|
|-lt|test num1 -lt num2|num1 が num2 より小ならば真となる。num1<num2|
|-le|test num1 -le num2|num1 が num2 以下ならば真となる。num1≦num2|
|-gt|test num1 -gt num2|num1 が num2 より大ならば真となる。num1>num2|
|-ge|test num1 -ge num2|num1 が num2 以上ならば真となる。|
			
