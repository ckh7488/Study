## LongestPalindrome  
### 개요  
가장 긴 앞뒤가 같은 문자열을 찾는 문제.  
`input` :  str  (문자열)  
정확한 문제 설명은 이름을 쳐보면 자세히 나온다.  
  
### 풀이 1  
단순하면서 느린 풀이이다.  
str의 길이를 N으로 생각할 때,  
N의 1번째 원소부터, for문을 두번돌린다.  
양쪽 끝이 같은 문자열을 찾고, 그 문자열이 앞뒤가 같은 문자열인지 체크하는 방법이다.  

### 풀이 2  
`DP`를 이용한다.  
어떤 문자열이 palindrome(회문)인지 확인하는 방법을 알고리즘 적으로 생각하면,  
> 1   양쪽 끝의 인덱스를 찾는다.  
> 2  가운데의 문자열이 palindrome인지 확인한다.  
> 3  양쪽 끝이 같은 문자열인지 확인한다.  
  
로 알 수 있다. 이 과정에서 `DP`를 사용하면 좀더 빠른 풀이가 가능하다.  
  
  
### 코드  
`LongestPalindrome.js` 파일 참조.  
   
    