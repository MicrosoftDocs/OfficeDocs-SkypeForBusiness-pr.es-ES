---
title: Configurar el uso de fotografías de alta resolución en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumen: Configurar el uso de fotografías de alta resolución en 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: 9d5117f2774a928e520aa211007fffb0740a2b52
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server-2015"></a>Configurar el uso de fotografías de alta resolución en Skype Empresarial Server 2015
 
**Resumen:** Configurar el uso de fotografías de alta resolución en 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.
  
En Skype para Business Server 2015 fotos pueden almacenarse en el buzón de un usuario 2016 de Exchange Server o Exchange Server 2013 que permite tamaños de foto hasta 648 x 648 píxeles. Además, Exchange Server puede cambiar automáticamente el tamaño estas fotos para su uso en diversos productos según sea necesario. Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:
  
- 64 píxeles por 64 píxeles, que es el tamaño usado por el atributo thumbnailPhoto de Active Directory. Si carga una foto en Exchange Server, Exchange creará automáticamente un píxel 64 por la versión de 64 píxeles de dicha foto y actualizar el atributo del usuario thumbnailPhoto. Sin embargo, tenga en cuenta que lo contrario no es cierto: Si actualiza manualmente el atributo thumbnailPhoto en Active Directory la foto en el buzón de Exchange del usuario no se actualizarán automáticamente.
    
- 96 x 96 píxeles, para el uso en 2013 de Microsoft Outlook Web App, Microsoft Outlook 2013, Skype para el negocio de la aplicación Web y Skype para el negocio.
    
- 648 x 648 píxeles para usar Skype para empresas y Skype para Business Web App Skype para el negocio de la aplicación Web.
    
> [!NOTE]
> Si dispone de los recursos, se recomienda que cargues fotos 648 x 648; proporciona la máxima resolución y calidad de imagen óptima en cualquier aplicación de Office 2013. Cada fotografía JPEG con un tamaño de 648 x 648 y una profundidad de 24 bits da como resultado un tamaño de aproximadamente 240 kilobytes. Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario. 
  
Se pueden cargar fotos de alta resolución que se tiene acceso mediante los servicios Web de Exchange, los usuarios que ejecutan Outlook Web App de 2013; los usuarios sólo pueden actualizar sus propias fotos. Los administradores, sin embargo, pueden actualizar la foto para cualquier usuario mediante el Shell de administración de Exchange y una serie de comandos de Windows PowerShell similares al siguiente:
  
```
$photo = ([Byte ] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData -Preview $photo -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

El primer comando del ejemplo anterior usa el cmdlet Get-Content para leer el contenido del archivo C:\Photos\Kenmyer.jpg y almacenar dichos datos en una variable denominada Preview$photo. En el segundo comando, el cmdlet Set-UserPhoto de Exchange se utiliza para cargar la foto y adjuntar esa foto a la cuenta de usuario de Ken Myer.
  
> [!NOTE]
> En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta. También puede hacer referencia a una cuenta de usuario usando otros identificadores, como la dirección SMTP del usuario o su nombre principal de usuario. Consulte la documentación para el cmdlet Set-UserPhoto en [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) para obtener más información
  
Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, haga clic en **Guardar** en la página Opciones o el administrador necesita ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Para comprobar que la nueva foto se asignó a la cuenta de usuario, Ken Myer puede iniciar sesión en Skype para el negocio, seleccione **Opciones**e, a continuación, seleccione **Mis imágenes**. La foto recién cargada tiene que mostrarse como la foto personal de Ken. Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Si el administrador puede ver la foto con Internet Explorer, pero el usuario no puede ver sus fotos en Skype para empresas puede haber un problema de conectividad con servicios Web de Exchange o con el servicio de detección automática de Exchange.
  
Tenga en cuenta también que es necesaria ninguna configuración adicional para poder disponer de esta foto en Skype para el negocio. En su lugar, la foto estará disponible inmediatamente después de que se ha cargado y se ha ejecutado el cmdlet Set-UserPhoto.
  

