#include <iostream>
#include <fstream>

int main() {
    int n, z;
    std::ifstream fin("C:\\in.txt");
    std::ofstream fout("C:\\out.txt");
    fin >> n;
    int* arr = new int[n];
    for (int i = 0; i < n; i++) {
        fin >> arr[i];
    }

    fin >> z;
    fout << z << std::endl;
    int* mass = new int[z];
    for (int j = 0; j < z; j++) {
        fin >> mass[j];
    }


    int tmp = mass[z - 1];
    for (int j = z - 1; j > 0; --j) {
           mass[j] = mass[j - 1];
    }
    mass[0] = tmp;
    for (int j = 0; j < z; j++) {
        mass[j];
        fout << mass[j] << " ";
    }


    fout << std::endl;

    fout << n << std::endl;
    fin >> n;
    int temp = arr[0];
    for (int i = 0; i < n; ++i)
    {
        if (i == n - 1)
        {
            arr[i] = temp;
        }
        else {
            arr[i] = arr[i + 1];
        }
        fout << arr[i] << " ";
    }

    fin.close();
    fout.close();
    delete[] arr;
    delete[] mass;
}