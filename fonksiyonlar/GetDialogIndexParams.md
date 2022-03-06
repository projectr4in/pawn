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
