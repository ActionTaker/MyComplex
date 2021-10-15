# MyComplex
![ex_screenshot](./div.svg)

![ex_screenshot](./+.svg)

![ex_screenshot](./mul.svg)

## Code
>
```
class Complex {
private:
  double real, img;
public:
  Complex(double real, double img) : real(real), img(img) {}
  Complex(const Complex& c) {real = c.real, img = c.img;}
  Complex operator+(const Complex& c) const;
  Complex operator-(const Complex& c) const;
  Complex operator*(const Complex& c) const;
  Complex operator/(const Complex& c) const;
  Complex& operator+=(const Complex& c);
  Complex& operator-=(const Complex& c);
  Complex& operator*=(const Complex& c);
  Complex& operator/=(const Complex& c);
  Complex& operator=(const Complex& c);
  void println() { std::cout << "( " << real << " , " << img << " ) " << std::endl; }
};
```

## Note
## Complex& Complex::operator+=(const Complex& c)
>
```
Complex& Complex::operator+=(const Complex& c)
{
  return (*this) = (*this) + c;
}
```
(this) + c 는 에서 연산값을 가진 임시객체가 생성된다. 그리고 나서 그 임시객체는 =연산자의 매개변수로 들어간다. 그값이 (this)에 그대로 복사된다. 그리고 (this) = (this) + c;의 부분은 (this) 를 반환한다 (레퍼런스). 그러므로 return (this) = (this) + c; 과같은 연산이 가능하다. 총 복사수는 (this) + c에서 한번만 일어난다.

