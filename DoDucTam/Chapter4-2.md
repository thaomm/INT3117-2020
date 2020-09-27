## file để test Calc.java

```
public class Calc
{
   static public int add (int a, int b)
   {
      return a + b;
   }
   
   static public int subtract (int a, int b){
       return a - b;
   }
   
   static public double divide(int a, int b){
       if(b == 0){
           throw new IllegalArgumentException("Can't divide by zero");
       }
       return a / b;
   }
   
   static public int multiply (int a, int b){
       return a* b;
   }
}
```

## file test CalcTest.java
```
import org.junit.Test;
import static org.junit.Assert.*;

public class CalcTest {
    
    public CalcTest() {
    }

    /**
     * Test of add method, of class Calc.
     */
    @Test
    public void testAdd() {
        System.out.println("add");
        int a = 2;
        int b = 3;
        int expect = 5;
        int res = Calc.add(a, b);
        assertEquals(expect, res);
    }
    
    @Test
    public void testSubtract() {
        System.out.println("subtract");
        int a = 1;
        int b = 2;
        int expect = 3;
        int res = Calc.subtract(a, b);
        assertEquals(expect, res);
    }
    
    @Test
    public void testSubtractNegatives() {
        System.out.println("subtract negatives");
        int a = -1;
        int b = 2;
        int expect = -3;
        int res = Calc.subtract(a, b);
        assertEquals(expect, res);
    }
    
    @Test
    public void testMultiply() {
        System.out.println("multiply");
        int a = 1;
        int b = 2;
        int expect = 2;
        int res = Calc.multiply(a, b);
        assertEquals(expect, res);
    }
    
    @Test
    public void testDivide() {
        System.out.println("divide");
        int a = 10;
        int b = 2;
        double expect = 5;
        double res = Calc.divide(a, b);
        assertEquals(expect, res, 1);
    }
    
    @Test
    public void testDivideNonInteger() {
        System.out.println("divide non integer");
        int a = 1;
        int b = 2;
        double expect = 1/2;
        double res = Calc.divide(a, b);
        assertEquals(expect, res, 1);
    }
    
    @Test(expected = IllegalArgumentException.class)
    public void testDivideZero() {
        System.out.println("divide by zero");
        int a = 1;
        int b = 0;
        double res = Calc.divide(a, b);
    }
}
```
## Giải thích 

Ta cần thêm 2 operation mới là multiply và divide cho file Calc.java. Lúc đầu file test chỉ có một test cho operation add 

<img src="https://firebasestorage.googleapis.com/v0/b/ninja-firestore-tut-4fc86.appspot.com/o/test%20ban%20%C4%91%E1%BA%A7u.png?alt=media&token=c4d33b9e-845c-4484-89b2-e8f7ac0f63e9"
     alt="test ban đầu"
      />

Trước tiên, theo TDD, ta viết test cho các operation mới là subtract, divide và multiply nhưng nó sẽ fail vì ta chưa viết code function cho chúng

<img src="https://firebasestorage.googleapis.com/v0/b/ninja-firestore-tut-4fc86.appspot.com/o/th%C3%AAm%20test.png?alt=media&token=0c54bb1b-e453-4897-aaee-c1f886bf0db5"
     alt="thêm test"
      />

sau đó ta viết test cho cho operation subtract

<img src="https://firebasestorage.googleapis.com/v0/b/ninja-firestore-tut-4fc86.appspot.com/o/test%20subtract.png?alt=media&token=79930a50-d463-4bd0-82e7-f3d23e834bb8"
     alt="test substract"
      />

tiếp theo là operation divide, vấn để ở đây là hàm có thể trả về integer hoặc double. Theo TDD, ta làm cho chúng chạy đúng trước, lúc này hàm yêu cầu trả về integer

<img src="https://firebasestorage.googleapis.com/v0/b/ninja-firestore-tut-4fc86.appspot.com/o/test%20divide.png?alt=media&token=f5e8540f-efb7-478c-a5db-948eba5df728"
    alt="test divide"
    />

cuối cùng là hàm multiply. Ta cũng chỉ cho phép sử lý handle với input và output là integer thôi.

<img src="https://firebasestorage.googleapis.com/v0/b/ninja-firestore-tut-4fc86.appspot.com/o/test%20multiply.png?alt=media&token=50889301-b9fc-4dbd-a784-5676685aa07a"
    alt="test multiply"
    />

Ngoài ra ta cũng phải thêm cả trường hợp chia 2 integer nhưng kết quả là một non-integer, 1 test divide cho số 0 và 1 test với những số âm. 

<img src="https://firebasestorage.googleapis.com/v0/b/ninja-firestore-tut-4fc86.appspot.com/o/test%20%C4%91%E1%BA%B7c%20bi%E1%BB%87t.png?alt=media&token=3fee7251-6fb5-4c65-9d0e-9822348f0745"
    atl="test devide 0 and non integer"
    />


