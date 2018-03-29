---
title: Asignar un certificado de autenticación de servidor a servidor a Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumen: Asignar un certificado de autenticación de servidor a servidor de Skype para Business Server 2015.'
ms.openlocfilehash: 7bc697d9c45b55708ffb3fa20f04fbeb3eec9de9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server-2015"></a>Asignar un certificado de autenticación de servidor a servidor a Skype Empresarial Server 2015
**Resumen:** Asignar un certificado de autenticación de servidor a servidor de Skype para Business Server 2015.
  
Para determinar si es o no un certificado de autenticación de servidor a servidor ya ha sido asignado a Skype para Business Server 2015, ejecute el comando siguiente desde el Skype para el Shell de administración de servidor de negocios:
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Si no recibe información del certificado, necesita asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor. Como regla general, puede utilizarse cualquier Skype para certificados de servidor de negocios 2015 como su certificado de OAuthTokenIssuer; Por ejemplo, su Skype para certificado de servidor de negocios 2015 predeterminado también puede utilizarse como el certificado OAuthTokenIssuer. (El certificado de OAUthTokenIssuer también puede ser cualquier certificado de servidor Web que incluye el nombre de su dominio SIP en el campo Asunto.) Éstas son los dos requisitos principales para el certificado utilizado para la autenticación de servidor a servidor: 1) el mismo certificado debe configurarse como el certificado de OAuthTokenIssuer en todos los servidores frontales; y, 2) del certificado debe ser de al menos 2048 bits.
  
Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación. Después de haber solicitado y obtenido el nuevo certificado puede iniciar sesión en cualquiera de los servidores frontales y utilice un comando de Windows PowerShell similar a éste para importar y asignar ese certificado:
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado. Este procedimiento debe ejecutarse sólo una vez: el Skype para el servicio de replicación de Business Server creará automáticamente un conjunto de tareas programadas que descifrar y desplegar el certificado en todos los servidores frontales.
  
Como alternativa, puede utilizar un certificado existente como el certificado de autenticación de servidor a servidor. (Como se ha indicado, el certificado predeterminado puede utilizarse como certificado de autenticación de servidor a servidor). Recupera el valor de la propiedad de huella digital del certificado de forma predeterminada el siguiente par de comandos de Windows PowerShell y utiliza ese valor para predeterminar el certificado el certificado de autenticación de servidor a servidor:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

En el comando anterior, el certificado recuperado se configura para funcionar como el certificado de autenticación de servidor a servidor global; Esto significa que el certificado se replican en y utilizado por todos los servidores frontales. De nuevo, este comando se debe ejecutar sólo una vez y sólo en uno de los servidores frontales. Aunque todos los servidores frontales deben utilizar el mismo certificado, no debe configurar el certificado de OAuthTokenIssuer en cada servidor Front-End. En su lugar, configurar el certificado una vez y después dejó el Skype para el servidor de replicación del servidor de negocios 2015 se encargan de copiar ese certificado en cada servidor.
  
El cmdlet Set-CsCertificate toma el certificado en cuestión y configura inmediatamente dicho certificado para que actúe como el certificado actual de OAuthTokenIssuer. (Skype para Business Server 2015 conserva dos copias de un tipo de certificado: el certificado actual y la anterior.) Si necesita el nuevo certificado para iniciar inmediatamente para que actúe como el certificado OAuthTokenIssuer, a continuación, debe usar el cmdlet Set-CsCertificate.
  
También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado. "Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado. Por ejemplo, este comando recupera el certificado predeterminado y lo configura para que sea el certificado OAuthTokenIssuer actual a partir del miércoles, 01 de julio de 2015:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

El miércoles, 01 de julio de 2015, el nuevo certificado se configurará como el certificado OAuthTokenIssuer actual, y el "antiguo" certificado OAuthTokenIssuer se configurará como el certificado anterior.
  
Si no desea utilizar Windows PowerShell también puede utilizar la consola de MMC certificados para exportar un certificado desde un servidor de Front-End y, a continuación, importar ese mismo certificado en todos los demás servidores frontales. Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.
  
> [!CAUTION]
> En este caso, el procedimiento debe realizarse en cada servidor Front-End. Al exportar e importar certificados de esta manera Skype para Business Server 2015 no replicarán ese certificado en cada servidor Front-End. 
  
Después de que el certificado se ha importado a todos los servidores frontales, dicho certificado puede asignarse a continuación, utilizando el Skype para el Asistente para implementación de Business Server en lugar de Windows PowerShell. Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:
  
1. Haga clic en Inicio, seleccione todos los programas, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para el Asistente para implementación de Business Server**.
    
2. En el Asistente para implementación, haga clic en **instalación o actualización de Skype para el sistema de servidor empresarial**.
    
3. En Skype para Business Server 2015 página, haga clic en el botón **Ejecutar** en la rúbrica **paso 3: solicitar, instalar o asignar certificados**. Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.
    
4. En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.
    
5. En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.
    
6. En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.
    
7. En la página Resumen de asignación de certificados, haga clic en **Siguiente**.
    
8. En la página Ejecutar comandos, haga clic en **Finalizar**.
    
9. Cierre el Asistente para certificados y el Asistente para la implementación.
    

