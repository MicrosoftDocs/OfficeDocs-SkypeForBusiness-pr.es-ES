---
title: Configurar el uso de fotos de alta resolución en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumen: configure el uso de fotos de alta resolución en Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online y Skype Empresarial Server.'
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834010"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurar el uso de fotos de alta resolución en Skype Empresarial Server
 
**Resumen:** Configure el uso de fotos de alta resolución en Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online y Skype Empresarial Server.
  
En Skype Empresarial Server, las fotos se pueden almacenar en el buzón de correo de Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online de un usuario, lo que permite tamaños de fotos de hasta 648 píxeles por 648 píxeles. Además, Exchange Server cambiar automáticamente el tamaño de estas fotos para usarlas en diferentes productos según sea necesario. Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:
  
- 64 píxeles por 64 píxeles, el tamaño usado para el atributo thumbnailPhoto de Active Directory. Si carga una foto en Exchange Server, Exchange creará automáticamente una versión de 64 píxeles por 64 píxeles de esa foto y actualizará el atributo thumbnailPhoto del usuario. Sin embargo, tenga en cuenta que lo contrario no es verdadero: si actualiza manualmente el atributo thumbnailPhoto en Active Directory, la foto del buzón de Exchange del usuario no se actualizará automáticamente.
    
- 96 píxeles por 96 píxeles, para su uso en Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype Empresarial Web App y Skype Empresarial.
    
- 648 píxeles por 648 píxeles para su uso en Skype Empresarial y Skype Empresarial Web App Skype Empresarial Web App.
    
> [!NOTE]
> Si tiene los recursos, se recomienda cargar fotos de 648 x 648; que proporciona la resolución máxima y la calidad de imagen óptima en cualquiera de las aplicaciones de Office 2013. Cada foto JPEG con un tamaño de 648 x 648 y una profundidad de 24 bits da como resultado un tamaño de archivo de aproximadamente 240 kilobytes. Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario. 
  
Los usuarios que ejecutan Outlook 2013 Web App pueden cargar fotos de alta resolución, a las que se accede mediante servicios Web Exchange; los usuarios solo pueden actualizar su propia foto. Sin embargo, los administradores pueden actualizar la foto de cualquier usuario mediante el Shell de administración de Exchange y una serie de comandos Windows PowerShell similares a los siguientes:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

El primer comando del ejemplo anterior usa el cmdlet para leer el contenido del archivo C:\Photos\Kenmyer.jpg almacenar los datos en una variable denominada `Get-Content` $photo. En el segundo comando, el cmdlet de Exchange se usa para cargar la foto y adjuntarla a la cuenta de usuario `Set-UserPhoto` de Ken Myer.
  
> [!NOTE]
> En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta. También puede hacer referencia a una cuenta de usuario usando otros identificadores como la dirección SMTP del usuario o su nombre principal de usuario. Consulte la documentación del cmdlet Set-UserPhoto para [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) obtener más información
  
Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, debe hacer clic en **Guardar** en la página Opciones o el administrador debe ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**. La foto recién cargada debe mostrarse como la foto personal de Ken. Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Si el administrador puede ver la foto con Internet Explorer, pero el usuario no puede ver su foto en Skype Empresarial, puede haber un problema de conectividad con los servicios Web Exchange o con el servicio de detección automática de Exchange.
  
Tenga en cuenta también que no es necesaria ninguna configuración adicional para que esta foto esté disponible en Skype Empresarial. En su lugar, la foto estará disponible al instante después de que se haya cargado y se `Set-UserPhoto` haya ejecutado el cmdlet.
