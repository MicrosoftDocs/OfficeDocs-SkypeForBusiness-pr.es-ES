---
title: Configurar el uso de fotos de alta resolución en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumen: configure el uso de fotos de alta resolución en Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.'
ms.openlocfilehash: 8d68cb75a053d7eb165383154514ca6ff8d1a941
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244328"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurar el uso de fotos de alta resolución en Skype empresarial Server
 
**Resumen:** Configure el uso de fotos de alta resolución en Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.
  
En Skype empresarial Server, las fotos se pueden almacenar en un buzón de correo de usuario de Exchange Server 2016 o de Exchange Server 2013, lo que permite un tamaño de foto de hasta 648 píxeles por 648 píxeles. Además, Exchange Server puede cambiar automáticamente el tamaño de estas fotos para usarlas en diferentes productos según sea necesario. Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:
  
- 64 píxeles por 64 píxeles, que es el tamaño usado por el atributo thumbnailPhoto de Active Directory. Si carga una foto a Exchange Server, Exchange creará automáticamente un píxel de 64 por 64 píxel de la foto y actualizará el atributo thumbnailPhoto del usuario. Sin embargo, ten en cuenta que el valor inverso no es verdadero: si actualizas manualmente el atributo thumbnailPhoto en Active Directory, no se actualizará automáticamente la foto en el buzón de Exchange del usuario.
    
- 96 píxeles por 96 píxeles, para su uso en Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, la aplicación Web de Skype empresarial y Skype empresarial.
    
- 648 píxeles por 648 píxeles para usarlos en Skype empresarial y en la aplicación Web de Skype empresarial para Skype empresarial.
    
> [!NOTE]
> Si tiene los recursos, le recomendamos que cargue 648 x 648 fotos. que proporciona la resolución máxima y una calidad de imagen óptima en cualquiera de las aplicaciones de Office 2013. Cada foto JPEG con un tamaño de 648 x 648 y una profundidad de 24 bits da como resultado un tamaño de archivo de aproximadamente 240 kilobytes. Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario. 
  
Las fotos de alta resolución, a las que se accede mediante servicios web Exchange, se pueden cargar mediante usuarios que ejecuten Outlook 2013 Web App; los usuarios solo pueden actualizar su propia foto. Los administradores, sin embargo, pueden actualizar la foto de cualquier usuario mediante el shell de administración de Exchange y una serie de comandos de Windows PowerShell similares a los siguientes:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

El primer comando del ejemplo anterior usa el `Get-Content` cmdlet para leer el contenido del archivo C:\Photos\Kenmyer.jpg y almacenar los datos en una variable denominada $Photo. En el segundo comando, se usa el `Set-UserPhoto` cmdlet de Exchange para cargar la foto y adjuntarla a la cuenta de usuario de Ken Myer.
  
> [!NOTE]
> En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta. También puede hacer referencia a una cuenta de usuario usando otros identificadores, como la dirección SMTP del usuario o su nombre principal de usuario. [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) Para obtener más información, consulte la documentación del cmdlet Set-UserPhoto.
  
Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, haga clic en **Guardar** en la página Opciones o el administrador necesita ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Para comprobar que la nueva foto se ha asignado a la cuenta de usuario, Ken Myer puede iniciar sesión en Skype empresarial, seleccionar **Opciones**y, a continuación, seleccionar **mi foto**. La foto recién cargada tiene que mostrarse como la foto personal de Ken. Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Si el administrador puede ver la foto con Internet Explorer pero el usuario no puede ver su foto en Skype empresarial, es posible que haya un problema de conectividad con los servicios Web de Exchange o con el servicio Detección automática de Exchange.
  
Tenga en cuenta que no es necesario realizar ninguna configuración adicional para que esta foto esté disponible en Skype empresarial. En su lugar, la foto estará disponible al instante una vez que se haya cargado y el `Set-UserPhoto` cmdlet se haya ejecutado.
