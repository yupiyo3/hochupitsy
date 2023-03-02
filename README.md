#include <iostream>
#include <math.h>
using namespace std;

enum Bibika { РАФ_977 = 1, ГАЗ_13, ЗАЗ_965,ИЖ_2125, ЗИЛ_111 = 0 };
Bibika operator+(const Bibika& m, const int& b)
{
    Bibika t = Bibika(b + m);

    return(t = Bibika(t % 5));
}

Bibika operator+(const int& b, const Bibika& m)
{
    return (m + b);
}
Bibika operator++(Bibika& m)
{
    return (m = Bibika(m + 1));
}
Bibika operator++(Bibika& m, int)
{
    Bibika t = m; m = Bibika(m + 1);
    return t;
}
void print(const Bibika& d)
{
    string Car[5] =
    {
        "РАФ-977","ГАЗ-13","ЗАЗ-965","Иж-2125","ЗИЛ-111"
    };
    cout << Car[d] << endl;
};

int main()
{
    setlocale(LC_ALL, "Rus");


    Bibika m = ИЖ_2125;
    print(m + 1);
    print(2 + m);
    print(operator+(m, 1));
    print(operator+(2, m));
    m++;
    print(m);
    print(++m);
    print(operator++(m));
    print(operator++(m, 0));
    print(m);

    system("pause");
}
