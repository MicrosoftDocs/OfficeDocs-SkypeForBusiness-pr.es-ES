---
title: Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: configurar la mensajería unificada de Exchange Server para el correo de voz de Skype empresarial Server.'
ms.openlocfilehash: affaf5eb25b755d51d4ce47dd75834b6704d7610
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797071"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server
 
**Resumen:** Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype empresarial Server.
  
Skype empresarial Server le permite almacenar mensajes de voz en Exchange Server 2016 o Exchange Server 2013; esos mensajes de voz aparecerán como mensajes de correo electrónico en las bandejas de los usuarios. 

> [!NOTE]
> La mensajería unificada de Exchange, tal como se conocía anteriormente, ya no está disponible en Exchange 2019, pero puede usar el sistema telefónico para grabar mensajes de voz y, a continuación, dejar la grabación en el buzón de Exchange de un usuario. Consulte [planear el servicio de buzón de voz en la nube](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obtener más información.
  
Si ya ha configurado la autenticación de servidor a servidor entre Skype empresarial Server y Exchange Server 2016 o Exchange Server 2013, estará listo para configurar la mensajería unificada. Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en el servidor Exchange. Por ejemplo, estos dos comandos (se ejecutan desde el shell de administración de Exchange) configurar un nuevo plan de marcado de 3 dígitos para Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "protegido" indica que el canal de señalización se cifra mediante la seguridad de la capa de transporte (TLS). El URIType "SipName" indica que los mensajes se enviarán y recibirán con el protocolo SIP, y la CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los Estados Unidos.
  
En el segundo comando, el valor de parámetro transferido al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos dentro del país que pueden utilizarse con este plan de marcado. El valor del parámetro "cualquier\*lugar\*,\*,," define lo siguiente:
  
- Nombre de grupo ("Anywhere")
    
- AllowedNumberString (\*un carácter comodín que indica que se permite cualquier cadena de número)
    
- DialNumberString (\*un carácter comodín que indica que se permite cualquier número marcado)
    
- TextComment (\*un carácter comodín que indica que se permite cualquier comando de texto)
    
> [!NOTE]
> Al crear un nuevo plan de marcado, también se crea una Directiva de buzón predeterminada. 
  
Después de crear y configurar el nuevo plan de marcado debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y luego modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Doble". Puede realizar estas dos tareas desde el shell de administración de Exchange:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Una vez configurado el servidor de mensajería unificada, debe ejecutar el cmdlet enable-ExchangeCertificate para asegurarse de que el certificado de Exchange se aplica al servicio de mensajería unificada:
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.
  
Tras finalizar de configurar el servidor de mensajería unificada puede configurar el Enrutador de llamadas de mensajería unificada:
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Puesto que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo donde se encuentre el Enrutador de llamadas de mensajería unificada.
  
Para completar la configuración de mensajería unificada, necesitará crear una directiva de buzón de correo de mensajería unificada y luego utilizar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo utilizando un comando similar a este:
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Y puede habilitar a un usuario para la mensajería unificada utilizando un comando similar a este:
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.
  
Una vez que haya habilitado su buzón de correo, el usuario kenmyer@litwareinc.com deberá poder utilizar la mensajería unificada de Exchange. Puede comprobar que el usuario se puede conectar a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) desde el shell de administración de Skype empresarial Server:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Si tiene un segundo usuario que ha sido habilitado para la mensajería unificada, puede utilizar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para verificar que este segundo usuario pueda dejar un mensaje de correo de voz para el primer usuario.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configuración de mensajería unificada en Microsoft Exchange Server 
> [!IMPORTANT]
> Si desea usar la mensajería unificada de Exchange (UM) para proporcionar respuesta de llamada, Outlook Voice Access o el operador automático para usuarios de Enterprise Voice, lea [plan para la integración de mensajería unificada de Exchange en Skype empresarial](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)y, a continuación, siga las instrucciones de esta sección. 

Para configurar la mensajería unificada de Exchange para que funcione con la telefonía IP empresarial, tendrá que realizar las siguientes tareas:

- Configurar certificados en el servidor que ejecuta los servicios de mensajería unificada (UM) de Exchange
  > [!NOTE]
  > Agregar todos los servidores de acceso de cliente y de buzón a todos los planes de marcado URI SIP de mensajería unificada. Si no es así, el enrutamiento de llamadas salientes no funciona según lo esperado. 
- Cree uno o varios planes de marcado URI SIP de MU, junto con los números de teléfono de acceso del suscriptor, según sea necesario y, a continuación, cree los planes de marcación de L correspondientes.

- Use el script ExchUCUtil. PS1 para:
    - Crear puertas de enlace IP de MU.
    - Crear grupos de extensiones de mensajería unificada.
    - Otorgue permiso de servidor de Skype empresarial para leer objetos de servicios de dominio de Active Directory de MU.
- Crear un objeto de operador automático de mensajería unificada.
- Crear un objeto de acceso de suscriptor.
- Crear un URI de SIP para cada usuario y asociar a los usuarios con un plan de marcado URI SIP de mensajería unificada.

### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Antes de empezar, en la documentación de esta sección se supone que ha implementado los siguientes roles de Exchange: acceso de cliente y buzón de correo. En Microsoft Exchange Server, la mensajería unificada de Exchange se ejecuta como un servicio en estos servidores.

Además, tenga en cuenta lo siguiente:
- Si la mensajería unificada de Exchange se instala en varios bosques, los pasos de integración del servidor de Exchange deben realizarse para cada bosque de MU. Además, cada bosque de MU debe estar configurado para confiar en el bosque en el que se implementa Skype empresarial Server y el bosque de whichSkype para empresas Server se debe configurar para que confíe en cada bosque de MU.
- Los pasos de integración se realizan en las funciones de Exchange Server donde se ejecutan los servicios de mensajería unificada y en el servidor que ejecuta Skype empresarial Server. Debe realizar los pasos de integración de mensajería unificada de Exchange Server antes de realizar los pasos de integración de Lync Server 2013.
  > [!NOTE]
  > Para ver qué pasos de integración se realizan en qué servidores y con qué roles de administrador, consulte [información general del proceso de implementación para integrar la mensajería unificada local y Skype empresarial](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Las siguientes herramientas deben estar disponibles en cada servidor que ejecute la mensajería unificada de Exchange:
- Shell de administración de Exchange
- El script ExchUCUtil. ps1, que realiza las siguientes tareas:
    - Crea una puerta de enlace IP de MU para cada servidor de Skype empresarial.
    - Crea un grupo de captura para cada puerta de enlace. El identificador piloto de cada grupo de captura especifica el plan de marcado URI SIP de MU usado por el grupo de servidores front-end o el servidor Standard Edition asociado a la puerta de enlace.
    - Concede permiso de servidor de Skype empresarial para leer los objetos de mensajería unificada de Exchange en servicios de dominio de Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Si está integrando Microsoft Skype empresarial Server con mensajería unificada de Exchange (UM), tiene que ejecutar el script ExchUcUtil. PS1 en el shell. El script ExchUcUtil. PS1 hace lo siguiente:

- Crea una puerta de enlace IP de MU para cada grupo de servidores de Skype empresarial.

> [!IMPORTANT]
> El script ExchUcUtil. PS1 crea una o varias puertas de enlace IP de MU. Debe deshabilitar las llamadas salientes en todas las puertas de enlace IP de MU excepto en una puerta de enlace creada por la secuencia de comandos. Esto incluye deshabilitar las llamadas salientes en las puertas de enlace IP de MU que se crearon antes de ejecutar el script. 

- Crea un grupo de captura de UM para cada puerta de enlace IP de MU. El identificador piloto de cada grupo de captura especifica el plan de marcado URI del SIP de MU usado por el grupo de servidores front-end de Skype empresarial Server o el servidor Standard Edition que está asociado a la puerta de enlace IP de MU.
- Concede permiso de servidor de Skype empresarial para leer objetos contenedores de mensajería unificada de Active Directory, como planes de marcado de MU, operadores automáticos, puertas de enlace IP de MU y grupos de captura de MU.
  > [!IMPORTANT]
  > Cada bosque de MU debe estar configurado para confiar en el bosque en el que se implementa Skype empresarial Server y el bosque en el que se implementa Skype empresarial Server 2013 debe estar configurado para confiar en cada bosque de MU. Si la mensajería unificada de Exchange se instala en varios bosques, los pasos de integración de Exchange Server deben realizarse para cada bosque de MU o tendrá que especificar el dominio de Skype empresarial Server. Por ejemplo, ExchUcUtil. PS1: bosque: <Lync-Domain-Controller-FQDN>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Usar el shell para ejecutar el script ExchUcUtil. ps1

Ejecute el script ExchUcUtil. PS1 en cualquier servidor de Exchange de su organización que esté en la misma topología que Skype empresarial Server. Puede ejecutar el script desde un servidor de buzones de correo con el shell o puede ejecutar el script con Windows PowerShell remoto en un servidor de acceso de cliente. Si ejecuta el script en un servidor de acceso de cliente de su organización, el servidor de acceso de cliente establecerá como proxy la sesión remota de Windows PowerShell en un servidor de buzones de correo de la organización.
> [!IMPORTANT]
> El script ExchUcUtil. PS1 crea una o varias puertas de enlace IP de MU. Debe deshabilitar las llamadas salientes en todas las puertas de enlace IP de MU excepto en una puerta de enlace creada por la secuencia de comandos. Esto incluye deshabilitar las llamadas salientes en las puertas de enlace IP de MU que se crearon antes de ejecutar el script. Para deshabilitar las llamadas salientes en una puerta de enlace IP de MU, consulte deshabilitar las llamadas salientes en puertas de enlace IP de MU. 
> [!IMPORTANT]
> Debe tener los permisos de la función de administración de la organización de Exchange o ser miembro del grupo de seguridad administradores de la organización de Exchange para poder ejecutar el script. 

1. Abra el shell de administración de Exchange.
2. En el símbolo del sistema C:\Windows\System32, escriba la letra de la **unidad de cd \<>: \Archivos de Files\Microsoft\Exchange Server\V15\Scripts>. ExchUcUtil. PS1**y, a continuación, presione Entrar.

#### <a name="how-do-you-know-this-worked"></a>¿Cómo se sabe que ha funcionado?

Para comprobar que el script ExchUcUtul. PS1 se completó correctamente, haga lo siguiente:
- Use el cmdlet Get-UMIPGateway o el EAC para ver la nueva puerta de enlace o las puertas de enlace IP de MU que se crearon.
- Use el cmdlet Get-UMHuntGroup o el CEF para ver el nuevo grupo o los grupos de captura de mensajería unificada que se crearon.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurar certificados en el servidor que ejecuta la mensajería unificada de Exchange Server
 
Si ha implementado la mensajería unificada de Exchange (UM), como se describe en planear la integración de mensajería unificada de Exchange en Skype empresarial Server en la documentación de planeación, y desea proporcionar características de mensajería unificada de Exchange a los usuarios de voz empresarial de su organización, puede usar los procedimientos siguientes para configurar el certificado en el servidor que ejecuta la mensajería unificada de Exchange.

> [!IMPORTANT]
> En el caso de los certificados internos, tanto los servidores que ejecutan Skype empresarial Server como los servidores que ejecutan Microsoft Exchange deben tener certificados de entidad raíz de confianza que sean de confianza mutuamente. La entidad de certificación (CA) puede ser la misma o una entidad de certificación diferente, siempre que los servidores tengan el certificado raíz de la entidad de certificación registrado en su almacén de certificados de entidad de certificación raíz de confianza. 

El servidor de Exchange debe estar configurado con un certificado de servidor para poder conectarse a Skype empresarial Server:
1. Descargue el certificado de CA para el servidor de Exchange.
2. Instale el certificado de CA para el servidor de Exchange.
3. Compruebe que la entidad emisora de certificados se encuentra en la lista de entidades emisoras raíz de confianza del servidor de Exchange.
4. Cree una solicitud de certificado para el servidor de Exchange e instale el certificado. 
5. Asigne el certificado para el servidor de Exchange.


**Para descargar el certificado de la entidad emisora:**

1. En el servidor que ejecuta la mensajería unificada de Exchange, haga clic en **Inicio**, haga clic en **ejecutar**, escriba **http://\<nombre del servidor de la CA emisora>/certsrv**y, a continuación, haga clic en **Aceptar**.
2. En seleccionar una tarea, haga clic en **descargar un certificado de CA, una cadena de certificados o una CRL**.
3. En **descargar un certificado de CA, una cadena de certificados o una CRL**, seleccione el **método de codificación para base 64**y, después, haga clic en**Descargar certificado de CA**.
   > [!NOTE]
   > También puede especificar la codificación de las reglas de codificación distintivas (DER) en este paso. Si selecciona la codificación DER, el tipo de archivo en el paso siguiente de este procedimiento y en el paso 10 de **para instalar el certificado de la entidad emisora** es. p7b en lugar de. cer. 
4. En el cuadro de diálogo **descarga de archivos** , haga clic en **Guardar**y, a continuación, guarde el archivo en el disco duro del servidor. (El archivo tendrá una extensión. cer o. p7b, en función de la codificación que haya seleccionado en el paso anterior).

**Para instalar el certificado de la entidad emisora:**

1. En el servidor que ejecuta la mensajería unificada de Exchange, abra Microsoft Management Console (MMC) haciendo clic en **Inicio**, haga clic en **Ejecutar**, escriba **MMC** en el cuadro Abrir y, a continuación, haga clic en **Aceptar**.
2. En el menú **archivo** , haga clic en **Agregar o quitar complemento**y, a continuación, haga clic en **Agregar**.
3. En el cuadro **Agregar complementos independientes** , haga clic en **certificados**y, a continuación, haga clic en **Agregar**.
4. En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y luego haga clic en **Siguiente**.
5. En el cuadro de diálogo **seleccionar equipo** , compruebe que la casilla **equipo local: (el equipo en el que se está ejecutando esta consola)** está activada y, a continuación, haga clic en **Finalizar**.
6. Haga clic en **cerrar**y, a continuación, en **Aceptar**. 
7. En el árbol de consola, expanda **certificados (equipo local)**, expanda **entidades emisoras raíz de confianza**y, a continuación, haga clic en **certificados**.
8. Haga clic con el botón secundario en **certificados**, seleccione **todas las tareas**y haga clic en **importar**.
9. Haga clic en **Siguiente**. 
10. Haga clic en **examinar** para buscar el archivo y, a continuación, haga clic en **siguiente**. (El archivo tendrá una extensión. cer o. p7b, en función de la codificación que haya seleccionado en el paso 3 de **para descargar el certificado de la entidad emisora**.
11. Haga clic en **colocar todos los certificados** en el siguiente almacén.
12. Haga clic en **examinar**y seleccione **entidades emisoras de certificados raíz de confianza**. 
13. Haga clic en **siguiente** para comprobar la configuración y, a continuación, haga clic en **Finalizar**. 


**Para comprobar que la entidad emisora se encuentra en la lista de entidades emisoras raíz de confianza:**

1. En el servidor que ejecuta la mensajería unificada de Exchange, en MMC expanda certificados (equipo local), expanda entidades emisoras raíz de confianza y, a continuación, haga clic en certificados.
2. En el panel de detalles, compruebe que la entidad emisora está en la lista de entidades emisoras de confianza.


