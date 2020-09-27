## **Question 1: Suppose that coverage criterion C1 subsumes coverage criterion C2.**

## **Further suppose that test set T1 satisfies C1 on program P, and test set T2 satisfies C2 , also on P.**
## **(a) Does T1 necessarily satisfy C2? Explain.**
## **(b) Does T2 necessarily satisfy C1? Explain.**
## **(c) If P contains a fault, and T2 reveals the fault, T1 does not necessarily also reveal the fault. Explain**

(a) Đề bài có điều kiện bao phủ C1 chứa điều kiện bao phủ C2, mà tập kiểm thử T1 thỏa mãn C1 nên sy ra tập kiểm thử T1 cũng sẽ thỏa mãn điều kiện bao phủ C2.

(b) Điều kiện bao phủ C1 chứa điều kiện bao phủ C2, nên điều kiện bao phủ C2 là một tập con của điều kiện bao phủ C1 nên không thể thỏa mãn hết những tập con khác trong C1. Do đó tập kiểm thử T2 không  thỏa mãn điều kiện bao phủ C1.

(c) Do tập kiểm thử T2 không phải là tập con của tập kiểm thử T1. Chúng không bao hàm mà tách biệt nhau nên khi chương trình P chứa lỗi, và tập kiểm thử T2 chỉ ra lỗi, tập kiểm thử T1 không c chỉ ra lỗi. 
