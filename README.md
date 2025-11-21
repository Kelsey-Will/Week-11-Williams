#include <iostream>
#include <stdexcept>
using namespace std;

template <typename T>
class Number {
private:
    T value;
public:
    Number(T v) : value(v) {}

    Number operator+(const Number& other) {
        return Number(this->value + other.value);
    }

    void riskyDivide(T divisor) {
        try {
            if (divisor == 0) {
                throw runtime_error("divide by zero");
            }
            cout << value / divisor << endl;
        }
        catch (runtime_error& e) {
            cout << "Error: " << errorMsg << endl; // error: 'errorMsg' not defined
        }
    }
};

int main() {
    Number<int> n1(10), n2(x); // error: 'x' not declared
    Number<int> n3 = n1 + n2;
    n3.riskyDivide(0);
    return 0;
}
