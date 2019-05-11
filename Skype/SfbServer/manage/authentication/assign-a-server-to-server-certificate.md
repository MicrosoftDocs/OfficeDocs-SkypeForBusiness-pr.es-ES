---
title: Asignar un certificado de autenticación de servidor a servidor a Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumen: Asignar un certificado de autenticación de servidor a servidor para Skype para Business Server.'
ms.openlocfilehash: 761234f821f5d95d53f7188a7197b28710d23893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902758"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Asignar un certificado de autenticación de servidor a servidor a Skype para Business Server
**Resumen:** Asignar un certificado de autenticación de servidor a servidor para Skype para Business Server.
  
Para determinar si un certificado de autenticación de servidor a servidor ya ha sido asignado a Skype para Business Server, ejecute el siguiente comando desde el Skype para Shell de administración de servidor empresarial:
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Si no recibe información del certificado, necesita asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor. Como regla general, se puede usar cualquier Skype para el certificado de servidor empresarial como su certificado OAuthTokenIssuer; Por ejemplo, su Skype para certificado predeterminado de Business Server también puede usarse como el certificado OAuthTokenIssuer. (El certificado OAUthTokenIssuer también puede ser cualquier certificado de servidor Web que incluye el nombre de su dominio SIP en el campo Asunto.) Éstas son los dos requisitos para el certificado usado para la autenticación de servidor a servidor principales: 1) el mismo certificado debe configurarse como el certificado OAuthTokenIssuer en todos los servidores Front-End; y, 2) el certificado debe ser de al menos 2048 bits.
  
Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación. Después de haber solicitado y obtenido el nuevo certificado, a continuación, inicie sesión en cualquiera de los servidores Front-End y use un comando de Windows PowerShell similar a esta para importar y asignar ese certificado:
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado. Este procedimiento se debe ejecutar una sola vez: el Skype para el servicio de replicación de Business Server, a continuación, creará automáticamente un conjunto de las tareas programadas que se descifrar e implementará el certificado a todos los servidores Front-End.
  
Como alternativa, puede usar un certificado existente como su certificado de autenticación de servidor a servidor. (Tal y como se ha mencionado, el certificado predeterminado puede usarse como el certificado de autenticación de servidor a servidor). El siguiente par de comandos de Windows PowerShell recupera el valor de propiedad de huella digital del certificado de forma predeterminada, a continuación, usar ese valor para realizar el valor predeterminado del certificado el certificado de autenticación de servidor a servidor:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

En el comando anterior, el certificado recuperado se configura para que funcione como el certificado de autenticación de servidor a servidor global; Eso significa que el certificado se replican en y utilizado por todos los servidores Front-End. Una vez más, este comando se debe ejecutar sólo una vez y sólo en uno de los servidores Front-End. Aunque todos los servidores Front-End debe usar el mismo certificado, no debe configurar el certificado OAuthTokenIssuer en cada servidor Front-End. En su lugar, configure el certificado una vez, a continuación, permiten la Skype para servidor de replicación de Business Server tenga cuidado de copiar ese certificado a cada servidor.
  
El cmdlet Set-CsCertificate toma el certificado en cuestión y configura inmediatamente ese certificado para que actúen como el certificado OAuthTokenIssuer actual. (Skype para Business Server mantiene dos copias de un tipo de certificado: el certificado actual y el certificado anterior.) Si necesita el nuevo certificado para iniciar inmediatamente para que actúe como el certificado OAuthTokenIssuer, a continuación, debe usar el cmdlet Set-CsCertificate.
  
También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado. "Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado. Por ejemplo, este comando recupera el certificado predeterminado y lo configura para que sea el certificado OAuthTokenIssuer actual a partir del miércoles, 01 de julio de 2015:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

En el 1 de julio de 2015, el nuevo certificado se configurará como el certificado OAuthTokenIssuer actual y el "antiguo" certificado OAuthTokenIssuer se configurará como el certificado anterior.
  
Si no desea usar Windows PowerShell también puede usar la consola MMC de certificados para exportar un certificado desde un servidor Front-End y, a continuación, importar ese mismo certificado en todos los otros servidores Front-End. Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.
  
> [!CAUTION]
> En este caso, el procedimiento debe realizarse en cada servidor Front-End. Al exportar e importar certificados de esta manera Skype para Business Server no replicará ese certificado a cada servidor Front-End. 
  
Después de importar el certificado a todos los servidores Front-End, a continuación, se puede asignar ese certificado utilizando el Skype para el Asistente para la implementación de servidor de negocio en lugar de Windows PowerShell. Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:
  
1. Haga clic en Inicio, haga clic en todos los programas, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para el Asistente para la implementación de servidor de negocio**.
    
2. En el Asistente para la implementación, haga clic en **instalar o actualización de Skype para Business Server System**.
    
3. En Skype para página Business Server, haga clic en el botón **Ejecutar** bajo el encabezado **paso 3: solicitar, instalar o asignar certificados**. Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.
    
4. En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.
    
5. En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.
    
6. En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.
    
7. En la página Resumen de asignación de certificados, haga clic en **Siguiente**.
    
8. En la página Ejecutar comandos, haga clic en **Finalizar**.
    
9. Cierre el Asistente para certificados y el Asistente para la implementación.
    

