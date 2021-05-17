# Job scheduling

## 201902949 이정수

--------------------------------------------------

## Job scheduling 문제

 n개의 작업과 각 작업의 수행시간인 t1, t2, t3, ...,  tn이 있고 m개의 기계가 주어질때 작업 스케줄링 문제는 수행 시간이 중복되지 않도록 작업이 가장 빨리 종료될 수 있게 모든 작업을 기계에 배정하는 문제이다.
한 작업은 배정된 기계에서 연속적으로 수행되어야 하고 기계는 한 번에 하나의 작업만을 수행할 수 있다.

작업을 가장 빨리 종료하기 위해서는 그리디 알고리즘을 이용하는데 현재까지 배정된 작업에 대해 가장 빨리 끝나는 기계에 새 작업을 배정하는 방법을 사용한다. 해당 알고리즘은 아래와 같다.


public class Jobscheduling 
{
    for j = 1 to m
    L[j] = 0
        // L[j] = 기계 M_j에 배정된 마지막 작업의 종료 시간 
for i = 1 to n
    { min = 1
        for j = 2 to m
        {          //가장 일찍 끝나는 기계를 찾음
            if (L[j] < L[min])
                min = j
        } //    작업 i를 기계 M_min에 배정함
        L[min] = L[min] + t_i
    } 
return //가장 늦은 작업 종료 시간

}


