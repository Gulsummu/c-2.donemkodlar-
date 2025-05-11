# c-2.donemkodlar-

#include <iostream>
#include<string>
#include<fstream> //ofstream yazma için //ifstream okuma için kullanılır
using namespace std;
///////////////////////////////////////3. hafta
/*int main()
{
	ofstream dosyaYaz("ornek.txt" , ios:: app);//yeni birsey yazacakasak app kulanıyoruz
	if (!dosyaYaz.is_open()) {
		cout << "dosya acilaamadi";// cerr cout un hata mesajı eror veriyor yani
	}
	else {
		dosyaYaz << "dosya acildi" << endl;
	}
	dosyaYaz.close();

	//********************************

	ifstream dosyaOku("ornek.txt");
	if (dosyaOku.is_open()) {
		string satir;
		while (getline(dosyaOku , satir)) {
			cout << satir << endl;
		}
		dosyaOku.close();
	}
	else {
		cout << "dosya acilmadi";
	}
	return 0;
}*/

// getline (dosya , satir)
//ekleme silme
///////////////////////////////////////////////////////// 4.hafta
/*int main()
{
	string str = "defne";
	string str1("dunya");
	string str2(5, 'w');
	string str4 = str + str1 + str2;
	cout << str<<str1<<str2;
	// boyut fonksyonları
	string str5 = "c++ string";
	cout << str5.length() << endl;
	str5 = "c++";
	str5.shrink_to_fit();// str5 suan olan ifadeyi düzenle
	str5.reserve();
	cout << str5.capacity() << endl;
	cout << str5.size() << endl;
	//str5.clear();
	if (!str5.empty())
	{
		cout << "dolu" << endl;
	}
	//ekleme yerdeğiştirme ve silme metodu
	string str6 = "merhaba";
	str6.append("programlama");// str5+= "programlama
	cout << str6 << endl;
	str6.insert(3, "diliyle");
    cout << str6 << endl;
	str6.erase(8,5);
	cout << str6 << endl;
	str6.replace(8, 5, "irmak" , 0 , 5);//insert ve erase metodunun birleşmiş hali gibi
	cout << str6 << endl;
	string str7 = str6.substr(8 ,7);//alt parçalarına ayırır
	cout << str7 << endl;
	//arama işlemleri
	string str8 = "abc abc abc";
	int indis = str6.find("irmak");
	if (indis != string::npos) // npos benbişeyler bulamadım demek
	{
		cout << "aranan deger " << indis << ". i ndiste bulunmadı" << endl;
	}
	int indis2 = str8.rfind("abc");

	if (indis != string::npos) // rfind ve findin farkı biri baştan aramaya başlıyor diğeri sondan 
	{
		cout << "aranan deger " << indis << ". i ndiste bulunmadı" << endl;
	}string str9 = "ali";
	string str10 = "veli";
	int sonuc = str9.compare(str10);
	if (str7.compare(str8))
	{

	}
	//erişim yöntemleri
	cout << str10[1];//indili erişim
	cout << str10.at(0);//metot ile
	string str11 = "10.4";
	int deger = stoi(str11);
	float deger = stof(str11);
	int deger2 = 10;
	string str12 = to_string(deger2);
	//dongüler
	for (int i = 0; i < str7.length(); i++)
	{
		cout << str7.at(i) << " ";
	}
	for (char var:str7)
	{
		cout << var << " ";
	}
	return 0;
}*/
//////////////////////////////////////////5.hafta
//pointrlar
/*void swep(int* m, int* n)
{
	int temp = *m;
	*m = *n;
	*n = temp;
}
int main()
{
	int x = 10;
	int y = 20;
	cout << "fonksyondan once x = " << x << "y = " << y << endl;
	swep(&x, &y);
	cout << "fonksyondan sonra x = " << x << "y = " << y << endl;


	int* ptr;
	int a = 5;
	ptr = &a;
	cout << "A nin degeri " << a << endl;
	cout << "A nin aderesi" << ptr << endl;
	cout << "A nin adresi " << &a << endl;
	cout << "ptr nin degeri " << *ptr << endl;
	*ptr = 10;
	cout << "A nin degeri " << a << endl;
	int arr[] = { 10,20,30 };
	int* ptr2 = arr;
	cout << "dizinin ilk elemani " << *ptr2 << endl;
	ptr2++;
	cout << "dizinin ikinci elemani " << *ptr2 << endl;
	ptr2++;
	cout << "dizinin ucuncu elemani " << *ptr2 << endl;

	char s1[] = "pointer";
	char* ptr3 = s1;
	while (*ptr3 == '\0') {
		cout << "ptr3 degeri " << *ptr3;
		ptr3++;
	}
	/*cout << endl;
	int* ptr4 = new int;
	*ptr4 = 78;
	cout << "ptr4 degeri " << *ptr4;

	delete ptr4;
	int boyut;
	cout << endl << "bir boyuut girin ";
	cin >> boyut;
	int* ptr5 = new int[boyut];
	for (int i = 0; i < boyut; i++)
	{
		cin >> ptr5[i];
	}
	for (int i = 0; i < boyut; i++)
	{
		cout << ptr5[i] << " ";
	}
	delete[] ptr5;*/

	/*int b = 45;
	int* ptr6 = &b;
	int** ptr7 = &ptr;
	cout << "b nin degeri " << b << endl;
	cout << "b nin adersi " << ptr6 << endl;
	cout << "ptr nin degeri " << ptr7 << endl;

	return 0;
}*/
/////////************SIRALAMA*********/////////////////
////////selection (seçme) sort/////////////////

void printarry(int arr[], int size)
{
	for (int i = 0; i < size; i++)
	{
		cout << arr[i] << "\t";
	}
	cout << endl;
}
void bubbleshort(int arr[], int size)
{
	bool isshorting = true;
	for (int i = 0; i < size; i++)
	{
		for (int j = 0; j < size - i - 1; j++)
		{
			if (arr[j] > arr[j + 1]) {

				swap(arr[j], arr[j + 1]);
				isshorting = false;
			}
		}
		if (isshorting)
		{
			break;
		}
		printarry(arr, size);

	}
}
void selectionshort(int arr[] , int size)
{
	int minindis = 0;//bu imleç olsun
	for (int i = 0; i < size-1; i++)//bu da imleci kontrol eden döngü
	{
		minindis = i;
		for (int j = i+1; j <= size; j++) {
			if (arr[i] > arr[j]) {
				minindis = j;
			}
		}
		if (minindis != i) 
			swap(arr[i], arr[minindis]);
			printarry(arr, size);
		
	}
}

int main()
{
	int arr[] = { 2,3,1,4,8,6,9 };
	int size = sizeof(arr) / sizeof(arr[0]);//dizinin boyutunu hesaplama kaç bit alana kapladiğını buluyor
	printarry(arr, size);
	cout << endl << endl;
	selectionshort(arr, size);
	cout << endl;
	printarry(arr, size);
	bubbleshort(arr, size);


	return 0;
}
// buradan sonrası taner hocanın yazdırdığı kodlar
#include <iostream>
#include<vector>
#include<string>
#include<deque>
#include<map>
#include<list>
#include<set>
#include<queue>
#include<stack>
#include<locale.h>
using namespace std;
/*int lineer(int dizi[], int size, int aranan)
{
	for (int i = 0; i < size; i++)
	{

		if (dizi[i] == aranan) {
			return i;
		}
	}
	return -1;
}

int main()
{
	int dizi[] = { 10,25,30,45 ,50 };
	int boyut = sizeof(dizi) / sizeof(dizi[0]);
		int aranan;
	cout << "aranan sayiyi girnin " << endl;
	cin >> aranan;

	int sonuc = binary(dizi, boyut, aranan);

		if (sonuc != -1) {
			cout << aranan << "bulundu " << sonuc << ".indekste bulundu " << endl;

		}
		else
		{
			cout << "aranan bulunmadi";
		}
	return 0;
}*/
/*int binary(int dizi[], int sol, int sag, int aranan) {
	while (sol <= sag) {
		int orta = sol + (sag - sol) / 2;
		if (dizi[orta] == aranan) 
			return orta;
		
		else if (dizi[orta] < aranan) 
			sol = orta + 1;
		
		else
			sag = orta - 1;
	}
	return -1;
}*/
/*template<typename T>
T maxsimum(T a, T b)
{
	return (a > b) ?  a : b;
}
template<typename T>
void degistir(T& x, T &y)
{
	T temp = x;
	x = y;
	y = temp;
}
template<typename T>
double ortalama(T dizi[], int boyut) {
	T toplam = 0;
	for (int i = 0; i < boyut; ++i)
	{
		toplam += dizi[i];
	}
	return static_cast<double>(toplam) / boyut;
}
template <typename T>
bool esitmi(T a, T b )
{
	return a == b;
}
template<typename T>
void terscevir(T dizi[],int boyut) {
	for (int i = 0; i < boyut /2; ++i)
	{
	degistir( dizi[i] ,dizi[boyut -i -1]);
	}
	
}

int main()
{
	int secim = -1;
	while (secim != 0) {
		cout << "sablon fonksyonu secin: " << endl;
		cout << "1 - maxsimum \n";
		cout << "2 - degistir \n";
		cout << "3- ortalama \n";
		cout << " 4- esitlik \n";
		cout << "5 - dizi ters cevir \n ";
		cout << "0 - cikis\n";
		cout << "seciniz: ";
		cin >> secim;
		if (secim == 1) {
			int a = 10, b = 20;
			cout << "maxsimum: " << maxsimum(a, b) << endl;
		}
		else if (secim == 2) {
			int x = 5, y = 8;
			cout << "once : x = " << x << ",y= " << y << endl;
			degistir(x, y);
			cout << "sonra : x =  " << x << ",y= " << y << endl;

		}
		else if (secim == 3) {
			double d[] = { 1.2,3.4,5.6 };

		}
		else if (secim == 4) {
			int a[] = { 1,2,3 };
			int b[] = { 1,4,5 };
			cout << boolalpha << esitmi(a, b) << endl;
		}
		else if (secim == 5) {
			int sayilar[] = { 10,20,30,40 };
			terscevir(sayilar, 4);

		}

	}
	return 0;
}*/
// max bulma itarator
/*int main() {
	vector <int> sayilar;
	int adet, deger;
	cout << "kac adet sayi gireceksiniz " << endl;
	cin >> adet;
		for (int i = 0; i < adet; i++)
		{
			cout << i + 1 << "sayi girin " << endl;
			cin >> deger;
			sayilar.push_back(deger);
		}
	cout << "girdiginiz sayilar " << endl;

	for (vector<int>::iterator it = sayilar.begin(); it != sayilar.end(); ++it) {
		cout << *it << " ";

	}
	cout << endl;
	if (!sayilar.empty()) {
		vector<int >::iterator it = sayilar.begin();
		int max = *it;
		for (; it != sayilar.end(); ++it)
		{
			if (*it > max)
				max = *it;
		}
		cout << "enbuyuk sayi : " << max << endl;

	}
	else {
		cout << "vector bos " << endl;
	}
	return 0;
}*/

/*template <typename container>
void yazC(const container& con) {
	for (auto it = con.begin(); it != con.end(); ++it) {
		cout << *it << " ";
	}
	cout << endl;
}*/
template <typename C>
void yazC(const C& c) {
	for (auto it = c.begin(); it != c.end(); ++it) {
		cout << *it << " ";
	}
	cout << endl;
}
void dequeYaz() {
	deque<int> DE = {1,2,3};
	DE.push_front(0);
	DE.push_back(4);
	cout << "deque: ";
	yazC(DE);

}
void listYaz() {
	list<string > ad = { "ali " , "ayse" , "memet" };
	ad.push_front("zeynep");
	ad.sort();
	cout << "list :";
	yazC(ad);
}
void setYaz() {
	set<int> set1 = { 4,2,5,1,3,2 };
	cout << "set: ";
	yazC(set1);
}
void Mset() {
	multiset<int> mset = {2,3,2,1,4,3};
	cout << "multiset: ";
	yazC(mset);

}
void mapYaz() {
	map<string, int> yas = { {"ali" , 25} ,{"ayse" , 30} , {"asil" , 15} };
	cout << "map:";
	for (auto it = yas.begin(); it != yas.end(); ++it) {
		cout << it->first << ": " << it->second << endl;
	}
	

}
void Mmap() {
	multimap<string, int> grades;
	grades.insert({ "math", 90 });
	grades.insert({ "fen", 70 });
	grades.insert({ "fizik", 80 });
	grades.insert({ "kimya", 60 });

	cout << "Multimap içerikleri:" << endl;
	for (const auto& grade : grades) {
		cout << grade.first << ": " << grade.second << endl;
	}

}

void stackYaz() {
	stack<int> st;
	st.push(10); st.push(20); st.push(30);
	cout << "stack: ";
	stack<int> temp;
	while (!temp.empty()) {
		cout << temp.top() << endl;
		temp.pop();
	}
	cout << endl;
	
}
int main()
{
	int islem = -1;
	while (true) {
		cout << "yapmak istediginiz islemi secin:" << endl;
		cout << "1 . deque :" << endl;
		cout << "2 . list :" << endl;
		cout << "3 . set :" << endl;
		cout << "4 . multiset :" << endl;
		cout << "5 . map :" << endl;
		cout << "6 . multimap :" << endl;
		cout << "7 . stack :" << endl;
		cout << "0 cıkıs: " << endl;
		cout << "seçiminiz: ";
		cin >> islem;
		if (islem == 0) {
			cout << "programdan cikiliyor " << endl;
			break;
		}
		switch (islem)
		{
		case 1: 
			dequeYaz();
			break;
		case 2: 
			listYaz();
			break;
		case 3:
			setYaz();
			break;
		case 4:
			Mset(); 
			break;
		case 5:
			mapYaz();
			break;
		case 6:
			Mmap();
			break;
		case 7:
			stackYaz();
			break;
		
		default:
			cout << "tekrar deneyin " << endl;


		}
	}
	return 0;
}

