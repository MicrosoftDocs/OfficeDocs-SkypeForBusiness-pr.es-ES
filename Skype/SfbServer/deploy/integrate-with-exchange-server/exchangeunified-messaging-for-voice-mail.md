---
title: Configurar Exchange Server mensajería unificada para el correo de voz de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumen: configurar la Exchange Server mensajería unificada para el correo de voz de Skype Empresarial Server.'
ms.openlocfilehash: 24bad46103433f6af9caebbe1894b1b3b2aa83d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109826"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurar Exchange Server mensajería unificada para el correo de voz de Skype Empresarial Server
 
**Resumen:** Configurar Exchange Server mensajería unificada para el correo de voz de Skype Empresarial Server.
  
Skype Empresarial Server permite tener mensajes de correo de voz almacenados en Exchange Server 2016 o Exchange Server 2013; esos mensajes de correo de voz aparecerán como mensajes de correo electrónico en las bandejas de entrada de los usuarios. 

> [!NOTE]
> La mensajería unificada de Exchange como se conocía anteriormente ya no está disponible en Exchange 2019, pero aún puede usar sistema telefónico para grabar mensajes de correo de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.
  
Si ya ha configurado la autenticación de servidor a servidor entre Skype Empresarial Server y Exchange Server 2016 o Exchange Server 2013, estará listo para configurar la mensajería unificada. Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en su Exchange Server. Por ejemplo, estos dos comandos (que se ejecutan desde dentro del Shell de administración de Exchange) configuran un nuevo plan de marcado de 3 dígitos para Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor del parámetro "Secured" indican que el canal de señalización está cifrado mediante seguridad de la capa de transporte (TLS). El URIType "SipName" indica que los mensajes se enviarán y recibirán mediante el protocolo SIP, y el CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los Estados Unidos.
  
En el segundo comando, el valor del parámetro pasado al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos de países que se pueden usar con este plan de marcado. El valor del parámetro "Anywhere, \* , , " establece lo \* \* siguiente:
  
- Nombre del grupo ("Anywhere")
    
- AllowedNumberString ( , un carácter comodín que indica que se permite \* cualquier cadena numérica)
    
- DialNumberString ( , un carácter comodín que indica que se permite \* cualquier número marcado)
    
- TextComment ( , un carácter comodín que indica que se permite \* cualquier comando de texto)
    
> [!NOTE]
> La creación de un nuevo plan de marcado también creará una directiva de buzón predeterminada. 
  
Después de crear y configurar el nuevo plan de marcado, debe agregar el nuevo plan de marcado al servidor de mensajería unificada y, a continuación, modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Dual". Puede realizar ambas tareas desde el Shell de administración de Exchange:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Después de configurar el servidor de mensajería unificada, debe ejecutar el cmdlet Enable-ExchangeCertificate para asegurarse de que el certificado de Exchange se aplica al servicio de mensajería unificada:
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Una vez asignado correctamente el certificado, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.
  
Después de finalizar la configuración del servidor de mensajería unificada, puede configurar el enrutador de llamadas de mensajería unificada:
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Dado que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo que hospeda el enrutador de llamadas de mensajería unificada.
  
Para completar la configuración de mensajería unificada, debe crear una directiva de buzón de mensajería unificada y, a continuación, usar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón mediante un comando similar al siguiente:
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Además, puede habilitar un usuario para la mensajería unificada mediante un comando similar al siguiente:
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

En el comando anterior, el parámetro Extensions representa el número de extensión telefónica del usuario. En este ejemplo, el usuario tiene el número de extensión 100.
  
Después de habilitar su buzón, el usuario kenmyer@litwareinc.com debe poder usar la mensajería unificada de Exchange. Puede comprobar que el usuario puede conectarse a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity?view=skype-ps) desde el Shell de administración de Skype Empresarial Server:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Si tiene un segundo usuario habilitado para mensajería unificada, puede usar el cmdlet [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para comprobar que este segundo usuario puede dejar un mensaje de correo de voz para el primer usuario.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configuración de mensajería unificada en Microsoft Exchange Server 
> [!IMPORTANT]
> Si desea usar la mensajería unificada de Exchange (MU) para proporcionar servicios de contestación de llamadas, Outlook Voice Access o operadores automáticos para usuarios de Telefonía IP empresarial, lea [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)y, a continuación, siga las instrucciones de esta sección. 

Para configurar la mensajería unificada (MU) de Exchange para que funcione con Telefonía IP empresarial, deberá realizar las siguientes tareas:

- Configurar certificados en el servidor que ejecuta servicios de mensajería unificada (MU) de Exchange
  > [!NOTE]
  > Agregue todos los servidores de acceso de cliente y buzones de correo a todos los planes de marcado URI SIP de mensajería unificada. Si no es así, el enrutamiento de llamadas salientes no funcionará como se esperaba. 
- Cree uno o varios planes de marcado URI SIP de mensajería unificada, junto con los números de teléfono de acceso de suscriptor, según sea necesario y, a continuación, cree los planes de marcado L correspondientes.

- Use el script exchucutil.ps1 para:
    - Crear puertas de enlace IP de Mensajería unificada.
    - Crear grupos de extensiones de Mensajería unificada.
    - Conceda permiso a Skype Empresarial Server para leer objetos de servicios de dominio de Active Directory de mensajería unificada.
- Cree un objeto de operador automático de mensajería unificada.
- Crear un objeto de acceso de suscriptor.
- Cree un URI de SIP para cada usuario y asocie a los usuarios con un plan de marcado URI SIP de mensajería unificada.

### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Antes de comenzar, la documentación de esta sección supone que ha implementado los siguientes roles de Exchange: Acceso de cliente y Buzón de correo. En Microsoft Exchange Server, la mensajería unificada de Exchange se ejecuta como un servicio en estos servidores.

También debe tener en cuenta lo siguiente:
- Si la mensajería unificada de Exchange está instalada en varios bosques, Exchange Server los pasos de integración deben realizarse para cada bosque de mensajería unificada. Además, cada bosque de mensajería unificada debe configurarse para confiar en el bosque en el que se implementa Skype Empresarial Server y el bosque en el que se implementaSkype para Business Server debe configurarse para que confíe en cada bosque de mensajería unificada.
- Los pasos de integración se realizan tanto en los roles Exchange Server donde se ejecutan los servicios de mensajería unificada como en el servidor que ejecuta Skype Empresarial Server. Debe realizar los pasos de Exchange Server de integración de mensajería unificada antes de realizar los pasos de integración de Lync Server 2013.
  > [!NOTE]
  > Para ver qué pasos de integración se realizan en qué servidores y qué roles de administrador, vea  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Las siguientes herramientas deben estar disponibles en cada servidor que ejecute mensajería unificada de Exchange:
- Shell de administración de Exchange
- El script exchucutil.ps1, que realiza las siguientes tareas:
    - Crea una puerta de enlace IP de mensajería unificada para cada Skype Empresarial Server.
    - Crea un grupo de búsqueda para cada puerta de enlace. El identificador piloto de cada grupo de extensiones especifica el plan de marcado URI SIP de mensajería unificada usado por el grupo de servidores front-end o el servidor Standard Edition asociado a la puerta de enlace.
    - Concede permiso a Skype Empresarial Server para leer objetos de mensajería unificada de Exchange en servicios de dominio de Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configurar la mensajería unificada en Microsoft Exchange con ExchUCUtil.ps1 

Al integrar Microsoft Skype Empresarial Server con la mensajería unificada (UM) de Exchange, debe ejecutar el script ExchUcUtil.ps1 en el Shell. El script ExchUcUtil.ps1 hace lo siguiente:

- Crea una puerta de enlace IP de mensajería unificada para cada grupo de Skype Empresarial Server.

> [!IMPORTANT]
> El script ExchUcUtil.ps1 crea una o más puertas de enlace IP de Mensajería unificada. Debe deshabilitar las llamadas salientes en todas las puertas de enlace IP de Mensajería unificada excepto una puerta de enlace que creó la secuencia de comandos. Esto incluye deshabilitar las llamadas salientes de las puertas de enlace IP de Mensajería unificada que se crearon antes de ejecutar el script. 

- Crea un grupo de extensiones de mensajería unificada para cada puerta de enlace IP de MU. El identificador piloto de cada grupo de extensiones especifica el plan de marcado URI SIP de mensajería unificada usado por el grupo de servidores front-end de Skype Empresarial Server o el servidor Standard Edition asociado a la puerta de enlace IP de mensajería unificada.
- Concede permiso a Skype Empresarial Server para leer objetos de contenedor de mensajería unificada de Active Directory, como planes de marcado de mensajería unificada, operadores automáticos, puertas de enlace IP de mensajería unificada y grupos de extensiones de mensajería unificada.
  > [!IMPORTANT]
  > Cada bosque de mensajería unificada debe configurarse para confiar en el bosque en el que se implementa Skype Empresarial Server y el bosque en el que se implementa Skype Empresarial Server 2013 debe configurarse para que confíe en cada bosque de mensajería unificada. Si la mensajería unificada de Exchange está instalada en varios bosques, se deben realizar los pasos de integración de Exchange Server para cada bosque de mensajería unificada o deberá especificar el dominio de Skype Empresarial Server. Por ejemplo, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Usar el Shell para ejecutar el script ExchUcUtil.ps1

Ejecute el script ExchUcUtil.ps1 en cualquier servidor exchange de la organización que se encuentra en la misma topología que Skype Empresarial Server. Puede ejecutar el script desde un servidor de buzones de correo con el Shell, o bien ejecutarlo con el Windows PowerShell remoto en un servidor de acceso de cliente. Si ejecuta el script en un servidor de acceso de cliente de su organización, dicho servidor transferirá por proxy la sesión de Remote Windows PowerShell a un servidor de buzones de la organización.
> [!IMPORTANT]
> El script ExchUcUtil.ps1 crea una o más puertas de enlace IP de Mensajería unificada. Debe deshabilitar las llamadas salientes en todas las puertas de enlace IP de Mensajería unificada excepto una puerta de enlace que creó la secuencia de comandos. Esto incluye deshabilitar las llamadas salientes de las puertas de enlace IP de Mensajería unificada que se crearon antes de ejecutar el script. Para deshabilitar las llamadas salientes en una puerta de enlace IP de Mensajería unificada, consulte Deshabilitar las llamadas salientes de puertas de enlace IP de mensajería unificada. 
> [!IMPORTANT]
> Para ejecutar el script, debe tener los permisos del rol de administración de la organización de Exchange o ser miembro del grupo de seguridad de administradores de organización de Exchange. 

1. Abra el Shell de administración de Exchange.
2. En el símbolo del sistema C:\Windows\System32, escriba **cd \<drive letter> :\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1** y, a continuación, presione ENTRAR.

#### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que el script ExchUcUtul.ps1 se ha completado correctamente, haga lo siguiente:
- Use el cmdlet Get-UMIPGateway o el EAC para ver la nueva puerta o puertas de enlace IP de la mensajería unificada que se han creado.
- Use el cmdlet Get-UMHuntGroup o el EAC para ver el nuevo grupo o grupos de extensiones de la mensajería unificada que se han creado.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurar certificados en el servidor que ejecuta Exchange Server mensajería unificada
 
Si ha implementado la mensajería unificada (UM) de Exchange, tal como se describe en Planning for Exchange Unified Messaging integration in Skype for Business Server en la documentación sobre planeación, y desea proporcionar características de mensajería unificada de Exchange Telefonía IP empresarial los usuarios de su organización, puede usar los siguientes procedimientos para configurar el certificado en el servidor que ejecuta mensajería unificada de Exchange.

> [!IMPORTANT]
> Para los certificados internos, tanto los servidores que ejecutan Skype Empresarial Server como los servidores que ejecutan Microsoft Exchange deben tener certificados de entidad de certificación raíz de confianza que sean de confianza mutua. La entidad de certificación (CA) puede ser la misma o una entidad de certificación diferente, siempre que los servidores tengan el certificado raíz de la entidad de certificación registrado en su almacén de certificados de entidad raíz de confianza. 

El Exchange Server debe configurarse con un certificado de servidor para conectarse a Skype Empresarial Server:
1. Descargue el certificado de ca para el Exchange Server.
2. Instale el certificado de ca para el Exchange Server.
3. Compruebe que la CA está en la lista de CA raíz de confianza de la Exchange Server.
4. Cree una solicitud de certificado para el Exchange Server e instale el certificado. 
5. Asigne el certificado para el Exchange Server.


**Para descargar el certificado de ca:**

1. En el servidor que ejecuta mensajería unificada de Exchange, haga clic en Inicio **,** haga clic en Ejecutar **,** escriba **http:// \<name of your Issuing CA Server> /certsrv** y, a continuación, haga clic en **Aceptar**.
2. En Seleccionar una tarea, haga **clic en Descargar un certificado de ca, cadena de certificados o CRL**.
3. En **Descargar un certificado de CA, cadena de certificados** o CRL , seleccione Método de codificación en Base **64** y, a continuación, haga clic **en Descargar certificado de CA**.
   > [!NOTE]
   > También puede especificar la codificación de reglas de codificación distinguidas (DER) en este paso. Si selecciona codificación DER, el tipo de archivo en el siguiente paso de este procedimiento y en el paso 10 de Para instalar el certificado de **ca** es .p7b en lugar de .cer. 
4. En el **cuadro de diálogo Descargar** archivo, haga clic en **Guardar** y, a continuación, guarde el archivo en el disco duro del servidor. (El archivo tendrá una extensión de archivo .cer o .p7b, según la codificación seleccionada en el paso anterior).

**Para instalar el certificado de ca:**

1. En el servidor que ejecuta mensajería unificada de Exchange, abra Microsoft Management Console (MMC) haciendo clic en Inicio **,** haciendo clic en **Ejecutar**, escribiendo **mmc** en el cuadro Abrir y, a continuación, haciendo clic en **Aceptar**.
2. En el menú **Archivo**, haga clic en **Agregar o quitar complemento** y, a continuación, en **Agregar**.
3. En el cuadro **Agregar complementos independientes**, haga clic en **Certificados** y, a continuación, en **Agregar**.
4. En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y, a continuación, haga clic en **Siguiente**.
5. En el **cuadro de diálogo** Seleccionar equipo, compruebe que la casilla Equipo **local: (el** equipo en el que se ejecuta esta consola) está activada y, a continuación, haga clic en **Finalizar**.
6. Haga clic en **Cerrar** y en **Aceptar**. 
7. En el árbol de consola, expanda **Certificados (equipo local),** expanda Entidades de certificación raíz **de** confianza y, a continuación, haga clic **en Certificados**.
8. Haga clic con el botón **secundario en Certificados,** haga clic **en Todas las tareas** y haga clic en **Importar**.
9. Haga clic en **Siguiente**. 
10. Haga **clic en** Examinar para buscar el archivo y, a continuación, haga clic en **Siguiente**. (El archivo tendrá una extensión de archivo .cer o .p7b, según la codificación seleccionada en el paso 3 de Para descargar el **certificado de ca**.
11. Haga **clic en Colocar todos los certificados** en el siguiente almacén.
12. Haga **clic en Examinar** y, a continuación, seleccione Entidades de certificación raíz de **confianza**. 
13. Haga **clic en** Siguiente para comprobar la configuración y, a continuación, haga clic en **Finalizar**. 


**Para comprobar que la CA está en la lista de CA raíz de confianza:**

1. En el servidor que ejecuta mensajería unificada de Exchange, en MMC expanda Certificados (equipo local), expanda Entidades de certificación raíz de confianza y, a continuación, haga clic en Certificados.
2. En el panel de detalles, compruebe que la CA está en la lista de CA de confianza.