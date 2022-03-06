
| Fonksiyon Adı | Parametreler |                                           İşlev                                           |
|---------------|--------------|-------------------------------------------------------------------------------------------|
| NewLine       | string[]     | Bir dosyanın satır sonu hatasını düzelterek içeriğini düzgün bir şekilde almanızı sağlar. |

### **Fonksiyon**
```c
NewLine(string[])
{
	new len = strlen(string);
	if(string[0] == 0) return;
    if((string[len - 1] == '\n') || (string[len - 1] == '\r')) 
	{
		string[len - 1] = 0;
		if(string[0] == 0) return;
		if((string[len - 2] == '\n') || (string[len - 2] == '\r'))
		{
			string[len - 2] = 0;
		}
	}
}
```

### **Kullanım**
```c
main()
{
    new
        // Dosyamızı açıyoruz
        File: dosya = fopen("metin.txt", io_read),
        
        // Açtığımız dosyadaki metinleri almak için değişken oluşturuyoruz
        buffer[256]
    ;
    if(dosya)
    {
        // Döngü yardımıyla dosyadaki verileri okuyoruz
        while(fread(dosya, buffer))
        {
            // Satır sonu hatasını düzeltiyoruz
            NewLine(buffer);

            // İçeriği konsola yazdırıyoruz
            printf(buffer);
        }

        // Açtığımız dosyayı kapatıyoruz
        fclose(dosya);
    }
}
```
