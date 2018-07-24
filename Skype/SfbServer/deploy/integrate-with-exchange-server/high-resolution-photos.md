---
title: Configurar el uso de fotografías de alta resolución en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumen: Configure el uso de fotografías de alta resolución en Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server.'
ms.openlocfilehash: 224c8dc238d8427deddc706b883614fd04c9b133
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21007240"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurar el uso de fotografías de alta resolución en Skype para Business Server
 
**Resumen:** Configurar el uso de fotografías de alta resolución en Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server.
  
En Skype para Business Server fotos pueden almacenarse en el buzón de un usuario 2016 de Exchange Server o Exchange Server 2013, lo que permite los tamaños de foto hasta 648 píxeles por 648 píxeles. Además, Exchange Server puede cambiar automáticamente el tamaño estas fotos para su uso en distintos productos según sea necesario. Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:
  
- 64 píxeles por 64 píxeles, que es el tamaño usado por el atributo thumbnailPhoto de Active Directory. Si se carga una foto en Exchange Server, Exchange crearán automáticamente un píxel 64 por la versión de 64 píxeles de dicha foto y actualizar el atributo del usuario thumbnailPhoto. Sin embargo, tenga en cuenta que lo contrario no es true: si se actualiza manualmente el atributo thumbnailPhoto en Active Directory la foto en el buzón de Exchange del usuario no se actualizarán automáticamente.
    
- 96 x 96 píxeles, para su uso en Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype para la aplicación empresarial de Web y Skype para la empresa.
    
- 648 píxeles por 648 píxeles, para usar en Skype para empresas y Skype para Business Web App Skype para la aplicación empresarial de Web.
    
> [!NOTE]
> Si dispone de los recursos, se recomienda que cargar fotografías 648 x 648; que proporciona la máxima resolución y la calidad de imagen óptima en cualquiera de las aplicaciones de Office 2013. Cada fotografía JPEG con un tamaño de 648 x 648 y una profundidad de 24 bits da como resultado un tamaño de archivo de aproximadamente 240 kilobytes. Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario. 
  
Se pueden cargar fotografías de alta resolución, que se puede tener acceso mediante el uso de servicios Web de Exchange, los usuarios que ejecutan Outlook 2013 Web App; los usuarios solo pueden actualizar su propia foto. Los administradores, sin embargo, pueden actualizar la foto para cualquier usuario mediante el Shell de administración de Exchange y una serie de comandos de Windows PowerShell similares al siguiente:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData -Preview $photo -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

El primer comando en el ejemplo anterior se usa el `Get-Content` cmdlet para leer el contenido del archivo C:\Photos\Kenmyer.jpg y almacenar los datos en una variable denominada $photo. En el segundo comando, el cmdlet de Exchange `Set-UserPhoto` se usa para cargar la foto y adjuntar esa foto a la cuenta de usuario de Ken Myer.
  
> [!NOTE]
> En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta. También puede hacer referencia a una cuenta de usuario usando otros identificadores, como la dirección SMTP del usuario o su nombre principal de usuario. Consulte la documentación para el cmdlet Set-UserPhoto en [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) para obtener más información
  
Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, haga clic en **Guardar** en la página Opciones o el administrador necesita ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Para comprobar que la nueva foto se asignó a la cuenta de usuario, Ken Myer puede iniciar sesión en Skype para la empresa, seleccione **Opciones**e, a continuación, seleccione **Mi foto**. La foto recién cargada tiene que mostrarse como la foto personal de Ken. Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Si el administrador puede ver la foto con el Explorador de Internet, pero el usuario no puede ver su propia foto en Skype para la empresa puede ser un problema de conectividad con los servicios Web de Exchange o con el servicio de detección automática de Exchange.
  
Tenga en cuenta también que es necesaria ninguna configuración adicional para poder realizar esta foto disponibles en Skype para la empresa. En su lugar, la foto estará disponible al instante después de que se haya cargado y la `Set-UserPhoto` se ha ejecutado el cmdlet.
