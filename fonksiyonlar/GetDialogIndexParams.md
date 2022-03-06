**[center]Dialog id indeksini almaya yarayan kısa bir fonksiyon. Örneğin: GetDialogIndexParams(1, 1, params[2]) gibi kendinize göre düzenleyebilirsiniz.[/center]**

```
GetDialogIndexParams(dialogid, index, params[])
{
	for(dialogid = 0; dialogid < index; dialogid++)
	{
		if(params[dialogid] >= 0 && params[dialogid] <= 65535)
		{
			return index++;
		}
	}
	return dialogid;
}
```
