# Module 9: Automating Integration with Azure Resources

# Demo: Viewing a Resource Group Template

1.  On the Start screen, click the down arrow to view all the applications, and then click **Windows PowerShell**.

1.  Switch to the **Windows PowerShell** console window.

1.  To sign in to Azure, type the following command in the console, and then press Enter:

	```
	Login-AzureRmAccount
	```

1.  In the **Sign in to Windows Azure** dialog box, perform the following steps:

	a.  Enter the email address of your Microsoft account.

	b.  Click **Continue**.

	c.  Enter the password for your Microsoft account.

	d.  Click **Sign In**.

1.  To create a new *Resource Group* named **20532Auto** with it's metadata located in the **West US** region, type the following command in the console, and then press Enter:

	```
	New-AzureRmResourceGroup -Name "20532Auto" -Location "West US"
	```

1.  To add a *Public IP Address* resource named **ExamplePIP** located in the **East US** region to the resource group, type the following command in the console, and then press Enter:

	```
	New-AzureRmResource -Location "East US" -ResourceName "ExamplePIP" -ResourceType "Microsoft.Network/publicIPAddresses" -ResourceGroupName "20532Auto" -Force
	```

1. To list all resources in the **20532Auto** *Resource Group*, type the following command in the console, and then press Enter:

	```
	Find-AzureRmResource -ResourceGroupNameContains "20532Auto"
	```

1.  To export the **20532Auto** *Resource Group* as a JSON template, type the following command in the console, and then press Enter:

	```
	Export-AzureRmResourceGroup -ResourceGroupName "20532Auto" -Path F:\Mod09\Demofiles
	```

1.  On the Start screen, click the **Desktop** tile.

1.  On the taskbar, click the **File Explorer** icon.

1.  In the Libraries window, go to **Allfiles (F):\\Mod09\\Demofiles**, and then view the content of the JSON file: **20532Auto.json**.

	> You can use either Visual Studio 2013 or Notepad to view the content of the JSON file.

1.  Close the **Microsoft Azure PowerShell** console window.
