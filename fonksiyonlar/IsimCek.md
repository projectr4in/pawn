
| Fonksiyon Adı | Parametreler |                    İşlev                    |
|---------------|--------------|---------------------------------------------|
| IsimCek       | playerid     | Sunucuda bulunan bir oyuncunun adını çeker. |

### **Fonksiyon**
```c
IsimCek(playerid)
{
    // Maksimum isim uzunluğunda bir değişken oluşturuyoruz
    new isim[MAX_PLAYER_NAME + 1];

    // Oyuncunun adını belirlediğimiz parametreye göre çekiyoruz
    GetPlayerName(playerid, isim, sizeof(isim));

    // Oyuncunun adını kullanmak istediğimiz yere gönderiyoruz
    return isim;
}
```

### **Kullanım**
```c
public OnPlayerConnect(playerid)
{
    // Değişken tanımlıyoruz
    new string[100];

    // Değişkenimizin içine yazımızı ve oyuncu adını yazdırıyoruz
    format(string, sizeof(string), "%s(%d), sunucuya giriş yaptı.", IsimCek(playerid), playerid);
    
    // Oyunda bulunan tüm oyunculara mesajı gönderiyoruz
    SendClientMessageToAll(-1, string);
    return 1;
}
```
