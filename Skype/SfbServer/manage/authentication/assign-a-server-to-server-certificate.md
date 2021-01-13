---
title: Asignar un certificado de autenticación de servidor a servidor a Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumen: asigne un certificado de autenticación de servidor a servidor para Skype Empresarial Server.'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828510"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Asignar un certificado de autenticación de servidor a servidor a Skype Empresarial Server
**Resumen:** Asignar un certificado de autenticación de servidor a servidor para Skype Empresarial Server.
  
Para determinar si ya se ha asignado un certificado de autenticación de servidor a servidor a Skype Empresarial Server, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Si no recibe información del certificado, debe asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor. Como regla general, cualquier certificado de Skype Empresarial Server puede usarse como certificado OAuthTokenIssuer; Por ejemplo, el certificado predeterminado de Skype Empresarial Server también puede usarse como certificado OAuthTokenIssuer. (El certificado OAUthTokenIssuer también puede ser cualquier certificado de servidor web que incluya el nombre de su dominio SIP en el campo Asunto). Los dos requisitos principales para el certificado usado para la autenticación de servidor a servidor son los siguientes: 1) el mismo certificado debe configurarse como certificado OAuthTokenIssuer en todos los servidores front-end; y, 2) el certificado debe tener al menos 2048 bits.
  
Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación. Una vez haya solicitado y obtenido el nuevo certificado, podrá iniciar sesión en cualquiera de los servidores front-end y usar un comando de Windows PowerShell similar a este para importar y asignar el certificado:
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado. Este procedimiento debe ejecutarse solo una vez: el servicio de replicación de Skype Empresarial Server creará automáticamente un conjunto de tareas programadas que descifrarán e implementarán el certificado en todos los servidores front-end.
  
También puede usar un certificado actual como certificado de autenticación de servidor a servidor. Como se ha mencionado, el certificado predeterminado se puede usar como certificado de autenticación de servidor a servidor. Los dos comandos siguientes de Windows PowerShell recuperan el valor de la propiedad Thumbprint del certificado predeterminado. Use este valor para que el certificado predeterminado sea el certificado de autenticación de servidor a servidor:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

En el comando anterior, el certificado recuperado está configurado para funcionar como el certificado de autenticación de servidor a servidor global; esto significa que el certificado se replicará en todos los servidores front-end y los usará. De nuevo, este comando solo debe ejecutarse una vez y solo en uno de los servidores front-end. Aunque todos los servidores front-end deben usar el mismo certificado, no debe configurar el certificado OAuthTokenIssuer en cada servidor front-end. En su lugar, configure el certificado una vez y, a continuación, deje que el servidor de replicación de Skype Empresarial Server se haga cargo de copiar ese certificado en cada servidor.
  
El Set-CsCertificate toma el certificado en cuestión e inmediatamente configura dicho certificado para que actúe como el certificado OAuthTokenIssuer actual. (Skype Empresarial Server mantiene dos copias de un tipo de certificado: el certificado actual y el certificado anterior). Si necesita que el nuevo certificado empiece a actuar inmediatamente como certificado OAuthTokenIssuer, debe usar el cmdlet Set-CsCertificate.
  
También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado. "Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado. Por ejemplo, este comando recupera el certificado predeterminado y, a continuación, configura dicho certificado para que se haga cargo del certificado OAuthTokenIssuer actual a partir del 1 de julio de 2015:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

El 1 de julio de 2015, el nuevo certificado se configurará como el certificado OAuthTokenIssuer actual y el certificado OAuthTokenIssuer "antiguo" se configurará como el certificado anterior.
  
Si no quiere usar Windows PowerShell, puede usar la consola MMC de certificados para exportar un certificado del servidor front-end e importarlo a todos los servidores front-end. Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.
  
> [!CAUTION]
> En tal caso, el procedimiento debe hacerse en cada servidor front-end. Al exportar e importar certificados de esta manera, Skype Empresarial Server no replicará ese certificado en cada servidor front-end. 
  
Después de importar el certificado a todos los servidores front-end, dicho certificado se puede asignar mediante el Asistente para la implementación de Skype Empresarial Server en lugar de Windows PowerShell. Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:
  
1. Haga clic en Inicio, en Todos los programas, **en Skype** Empresarial Server y, a continuación, en Asistente para la implementación de Skype **Empresarial Server.**
    
2. En el Asistente para la implementación, haga **clic en Instalar o actualizar el sistema de Skype Empresarial Server.**
    
3. En la página de Skype  Empresarial Server, haga clic en el botón Ejecutar bajo el encabezado **Paso 3: Solicitar,** instalar o asignar certificados. Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.
    
4. En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.
    
5. En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.
    
6. En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.
    
7. En la página Resumen de asignación de certificados, haga clic en **Siguiente**.
    
8. En la página Ejecución de comandos, haga clic en **Finalizar**.
    
9. Cierre el Asistente para certificados y el Asistente para la implementación.
    

