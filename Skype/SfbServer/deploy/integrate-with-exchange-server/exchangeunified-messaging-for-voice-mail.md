---
title: Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumen: Configurar la mensajería unificada de Exchange Server para Skype Business Server para correo de voz.'
ms.openlocfilehash: 21664f50b657324b4e70e86da83a4abbe1c14239
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979314"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server
 
**Resumen:** Configurar la mensajería unificada de Exchange Server para Skype Business Server para correo de voz.
  
Skype para Business Server permite que los mensajes de correo de voz almacenados en Exchange Server 2016 o Exchange Server 2013; los mensajes de correo de voz, a continuación, se mostrará como mensajes de correo electrónico en las bandejas de entrada de los usuarios. 

> [!NOTE]
> Mensajería unificada de Exchange como conocidos anteriormente ya no está disponible en Exchange 2019, pero puede seguir usando el sistema telefónico a los mensajes de correo de voz de registro y, a continuación, deje la grabación en el buzón de Exchange del usuario. Para obtener más información, vea [servicio de planeación de correo de voz en la nube](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) .
  
Si ya ha configurado la autenticación de servidor a servidor entre Skype para Business Server y Exchange Server 2016 o Exchange Server 2013, a continuación, está listo para configurar la mensajería unificada. Para ello, en primer lugar debe crear y asignar un nuevo plan de marcado de mensajería unificada en el servidor de Exchange. Por ejemplo, estos dos comandos (ejecutar desde dentro de la consola de administración de Exchange) configuración un nuevo plan de marcado de 3 dígitos para Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

En el primer comando en el ejemplo, el parámetro VoIPSecurity y el valor del parámetro "Secured" indica que el canal de señalización se cifra mediante el uso de seguridad de capa de transporte (TLS). La URIType "SipName" indica que se van a enviar los mensajes y reciben utilizando el protocolo SIP y el CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los Estados Unidos.
  
En el segundo comando, el valor de parámetro transferido al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos dentro del país que pueden utilizarse con este plan de marcado. El valor del parámetro "en cualquier lugar,\*,\*,\*" establece lo siguiente:
  
- Nombre de grupo ("Anywhere")
    
- AllowedNumberString (\*, un carácter comodín que indica que se permite cualquier cadena de números)
    
- DialNumberString (\*, un carácter comodín que indica que cualquier número marcado está permitido)
    
- TextComment (\*, un carácter comodín que indica que se permite cualquier comando de texto)
    
> [!NOTE]
> Al crear un nuevo plan de marcado, también se crea una Directiva de buzón predeterminada. 
  
Después de crear y configurar el nuevo plan de marcado debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y luego modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Doble". Puede realizar estas dos tareas desde dentro de la consola de administración de Exchange:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Después de que se ha configurado el servidor de mensajería unificada, debe ejecutar el cmdlet Enable-ExchangeCertificate para asegurarse de que su certificado de Exchange se aplica al servicio de mensajería unificada:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.
  
Tras finalizar de configurar el servidor de mensajería unificada puede configurar el Enrutador de llamadas de mensajería unificada:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Puesto que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo donde se encuentre el Enrutador de llamadas de mensajería unificada.
  
Para completar la configuración de mensajería unificada, necesitará crear una directiva de buzón de correo de mensajería unificada y luego utilizar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo utilizando un comando similar a este:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Y puede habilitar a un usuario para la mensajería unificada utilizando un comando similar a este:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.
  
Una vez que haya habilitado su buzón de correo, el usuario kenmyer@litwareinc.com deberá poder utilizar la mensajería unificada de Exchange. Puede comprobar que el usuario puede conectarse a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) desde dentro de la Skype para Shell de administración de servidor empresarial:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Si dispone de un segundo usuario que se ha habilitado para mensajería unificada puede usar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para comprobar que este segundo usuario puede dejar un mensaje de correo de voz para el primer usuario.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configuración de la mensajería unificada en Microsoft Exchange Server 
> [!IMPORTANT]
> Si desea usar la mensajería unificada de Exchange (UM) para proporcionar el contestador automático, Outlook Voice Access o servicios de operador automático para los usuarios de Enterprise Voice, leer [planeación para la integración de mensajería unificada de Exchange en Skype para la empresa](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)y, a continuación, siga el instrucciones de esta sección. 

Para configurar Exchange mensajería unificada (UM) para que funcione con Enterprise Voice, debe realizar las siguientes tareas:

- Configurar certificados en el servidor que ejecuta Servicios de mensajería unificada de Exchange (UM)
> [!NOTE]
> Agregue todos los servidores de buzones de correo y acceso de cliente a todos los planes de marcado de mensajería unificada URI de SIP. Si no, el enrutamiento de llamadas salientes no funciona como se esperaba. 
- Crear uno o varios URI de SIP de mensajería unificada de planes de marcado, junto con los números de teléfono de acceso de suscriptor, según sea necesario y, a continuación, crear los planes de marcado de L correspondientes.

- Use el script exchucutil.ps1 para:
    - Crear puertas de enlace IP de mensajería unificada.
    - Crear grupos de extensiones de mensajería unificada.
    - Concesión de Skype de permiso de Business Server para leer objetos de mensajería unificada de servicios de dominio de Active Directory.
- Crear un objeto de operador automático de mensajería unificada.
- Crear un objeto de acceso de suscriptor.
- Crear un URI de SIP para cada usuario y asociar usuarios con un plan de marcado de mensajería unificada URI de SIP.

### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Antes de empezar, en la documentación de esta sección se da por supuesto que ha implementado las siguientes funciones de Exchange: acceso de cliente y buzón de correo. En Microsoft Exchange Server, mensajería unificada de Exchange se ejecuta como un servicio en estos servidores.

También tenga en cuenta lo siguiente:
- Si la mensajería unificada de Exchange se instala en varios bosques, los pasos de integración de Exchange Server deben realizarse para cada bosque de mensajería unificada. Además, cada bosque de mensajería unificada debe configurarse para que confíe en el bosque en el que se implementa Skype para Business Server y el bosque en whichSkype para Business Server se implementa debe configurarse para que confíe en cada bosque de mensajería unificada.
- Los pasos de integración se realizan en los roles de servidor de Exchange donde se ejecutan servicios de mensajería unificada y en el servidor que ejecuta Skype para Business Server. Debe realizar los pasos de integración de mensajería unificada de Exchange Server antes de realizar los pasos de integración de Lync Server 2013.
> [!NOTE]
> Para ver qué pasos de integración se realizan en qué servidores y mediante qué roles de administrador, vea [información general del proceso de implementación para la integración de mensajería unificada y locales Skype para la empresa](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Las herramientas siguientes deben estar disponibles en cada servidor que ejecuta mensajería unificada de Exchange:
- Shell de administración de Exchange
- El script exchucutil.ps1, que realiza las tareas siguientes:
    - Crea una puerta de enlace IP de mensajería unificada para cada Skype para Business Server.
    - Crea un grupo de extensiones para cada puerta de enlace. El identificador piloto de cada grupo de búsqueda especifica el plan de marcado de mensajería unificada URI de SIP utilizado por el grupo de servidores Front-End o un servidor Standard Edition que está asociado con la puerta de enlace.
    - Concede Skype de permiso de Business Server para leer objetos de mensajería unificada de Exchange en los servicios de dominio de Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configurar la mensajería unificada de Microsoft Exchange con ExchUCUtil.ps1 

Cuando se está integra Microsoft Skype para Business Server con Exchange mensajería unificada (UM), tendrá que ejecutar el script ExchUcUtil.ps1 en el Shell. El script ExchUcUtil.ps1 hace lo siguiente:

- Crea una puerta de enlace IP de mensajería unificada para cada Skype para grupo de servidores empresariales.

> [!IMPORTANT]
> El script ExchUcUtil.ps1 crea uno o más puertas de enlace de IP de mensajería unificada. Debe deshabilitar las llamadas salientes en todas las puertas de enlace IP de mensajería unificada, excepto de una puerta de enlace que creó la secuencia de comandos. Esto incluye deshabilitar las llamadas salientes en las puertas de enlace IP de mensajería unificada que se crearon antes de que ejecutó la secuencia de comandos. 

- Crea un grupo de extensiones de mensajería unificada para cada puerta de enlace IP de mensajería unificada. El identificador piloto de cada grupo de búsqueda especifica el plan de marcado de mensajería unificada URI de SIP utilizado por el Skype de grupo empresarial servidor Front-End o un servidor Standard Edition que está asociado con la puerta de enlace IP de mensajería unificada.
- Concede a Skype de permiso de Business Server para leer los planes, operadores automáticos, las puertas de enlace IP de mensajería unificada de marcado de Active Directory contenedor objetos de mensajería unificada, como la mensajería unificada y grupos de extensiones de mensajería unificada.
> [!IMPORTANT]
> Cada bosque de mensajería unificada debe configurarse para que confíe en el bosque en el que se implementa Skype para Business Server y el bosque en el que se implementa Skype para Business Server 2013 debe configurarse para que confíe en cada bosque de mensajería unificada. Si la mensajería unificada de Exchange se instala en varios bosques, los pasos de integración de Exchange Server deben realizarse para cada bosque de mensajería unificada o tendrá que especificar el Skype para dominio Business Server. Por ejemplo, ExchUcUtil.ps1 – bosque: < lync dominio-controlador fqdn >. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Usar el Shell para ejecutar el script ExchUcUtil.ps1

Ejecute el script ExchUcUtil.ps1 en cualquier servidor de Exchange de la organización que se encuentra en la misma topología de Skype para Business Server. Puede ejecutar la secuencia de comandos de un servidor de buzón de correo mediante el Shell o bien puede ejecutar la secuencia de comandos con Windows PowerShell remoto en un servidor de acceso de cliente. Si ejecuta la secuencia de comandos en un servidor de acceso de cliente en la organización, el servidor de acceso de cliente va a proxy de la sesión de Windows PowerShell remoto para un servidor de buzones en la organización.
> [!IMPORTANT]
> El script ExchUcUtil.ps1 crea uno o más puertas de enlace de IP de mensajería unificada. Debe deshabilitar las llamadas salientes en todas las puertas de enlace IP de mensajería unificada, excepto de una puerta de enlace que creó la secuencia de comandos. Esto incluye deshabilitar las llamadas salientes en las puertas de enlace IP de mensajería unificada que se crearon antes de que ejecutó la secuencia de comandos. Para deshabilitar las llamadas salientes en una puerta de enlace IP de mensajería unificada, vea deshabilitar las llamadas en las puertas de enlace IP de mensajería unificada salientes. 
> [!IMPORTANT]
> Debe tener los permisos de la función de administración de la organización de Exchange o ser miembro del grupo de seguridad Administradores de organización de Exchange para ejecutar el script. 

1. Abra el Shell de administración de Exchange.
2. En el símbolo del sistema de C:\Windows\System32, escriba cd ** \<letra de unidad >: \Program Files\Microsoft\Exchange Server\V15\Scripts >. ExchUcUtil.ps1**, y, a continuación, presione ENTRAR.

#### <a name="how-do-you-know-this-worked"></a>¿Cómo sabrá funcionó?

Para comprobar que el script exchucutul.ps1 se ha completado correctamente, realice lo siguiente:
- Use el cmdlet Get-UMIPGateway o el CEF para ver la nueva puerta de enlace IP de mensajería unificada o puertas de enlace que se crearon.
- Use el cmdlet Get-UMHuntGroup o el EAC para ver el nuevo grupo de extensiones de mensajería unificada o los grupos que se crearon.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurar certificados en el servidor que ejecuta mensajería unificada de Exchange Server
 
Si ha implementado Exchange mensajería unificada (UM), tal como se describe en la planeación para la integración de mensajería unificada de Exchange en Skype para Business Server en la documentación de planeación y desea proporcionar características de mensajería unificada de Exchange a los usuarios de Enterprise Voice en su organización, puede usar los siguientes procedimientos para configurar el certificado en el servidor que ejecuta mensajería unificada de Exchange.

> [!IMPORTANT]
> Los certificados internos, los servidores que ejecutan Skype para Business Server y los servidores que ejecutan Microsoft Exchange deben ha confiado en certificados de entidad de certificación raíz que son de confianza mutuamente. La entidad de certificación (CA) puede ser la misma o una entidad de certificación diferente, siempre y cuando los servidores tienen el certificado de la entidad de certificación raíz registrado en su almacén de certificados de entidad de certificación raíz de confianza. 

El servidor de Exchange debe configurarse con un certificado de servidor para poder conectarse a Skype para Business Server:
1. Descargar el certificado de entidad emisora de certificados para el servidor de Exchange.
2. Instalar el certificado de entidad emisora de certificados para el servidor de Exchange.
3. Compruebe que la entidad de certificación está en la lista de entidades de certificación del servidor de Exchange de raíz de confianza.
4. Cree una solicitud de certificado para el servidor de Exchange e instalar el certificado. 
5. Asigne el certificado para el servidor de Exchange.


**Para descargar el certificado de entidad emisora de certificados:**

1. En el servidor que ejecuta mensajería unificada de Exchange, haga clic en **Inicio**, haga clic en **Ejecutar**, tipo **http://\<nombre de su servidor de entidad de certificación emitir > / certsrv**y, a continuación, haga clic en **Aceptar**.
2. En Seleccione una tarea, haga clic en **Descargar certificado de CA, cadena de certificados o CRL**.
3. En **Descargar certificado de CA, cadena de certificados o CRL**, seleccione el **Método de codificación en Base 64**y, a continuación, haga clic en**Descargar certificado de CA**.
> [!NOTE]
> También puede especificar la codificación de reglas de codificación distintivo (DER) en este paso. Si selecciona la codificación DER, el tipo de archivo en el siguiente paso de este procedimiento y en el paso 10 de **para instalar la entidad de certificación certificado** es. p7b en lugar de CER. 
4. En el cuadro de diálogo **Descarga de archivos** , haga clic en **Guardar**y, a continuación, guarde el archivo en el disco duro en el servidor. (El archivo tendrá una .cer o una extensión de archivo. p7b, según la codificación que haya seleccionado en el paso anterior.)

**Para instalar el certificado de entidad emisora de certificados:**

1. En el servidor que ejecuta mensajería unificada de Exchange, abra Microsoft Management Console (MMC) haciendo clic en **Inicio**, haciendo clic en **Ejecutar**, escriba **mmc** en el cuadro Abrir y, a continuación, haga clic en **Aceptar**.
2. En el menú **archivo** , haga clic en **Agregar o quitar complemento**y, a continuación, haga clic en **Agregar**.
3. En el cuadro **agregar complementos independientes** , haga clic en **certificados**y, a continuación, haga clic en **Agregar**.
4. En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y luego haga clic en **Siguiente**.
5. En el cuadro de diálogo **Seleccionar equipo** , compruebe que la **equipo Local: (el equipo que se está ejecutando esta consola)** casilla de verificación está activada y, a continuación, haga clic en **Finalizar**.
6. Haga clic en **Cerrar**y, a continuación, haga clic en **Aceptar**. 
7. En el árbol de consola, expanda **certificados (equipo Local)**, expanda **Entidades de certificación raíz de confianza**y, a continuación, haga clic en **certificados**.
8. Haga clic en **certificados**, haga clic en **Todas las tareas**y haga clic en **Importar**.
9. Haga clic en **Siguiente**. 
10. Haga clic en **Examinar** para buscar el archivo y, a continuación, haga clic en **siguiente**. (El archivo tendrá una .cer o una extensión de archivo. p7b, según la codificación que haya seleccionado en el paso 3 de **para descargar el certificado de entidad emisora de certificados**.
11. Haga clic en **Colocar todos los certificados** en el siguiente almacén.
12. Haga clic en **Examinar**y, a continuación, seleccione **Entidades de certificación raíz de confianza**. 
13. Haga clic en **siguiente** para comprobar la configuración y, a continuación, haga clic en **Finalizar**. 


**Para comprobar que la entidad de certificación está en la lista de entidades de certificación raíz de confianza:**

1. En el servidor que ejecuta mensajería unificada de Exchange, en MMC, expanda certificados (equipo Local), expanda entidades de certificación raíz de confianza y, a continuación, haga clic en certificados.
2. En el panel de detalles, compruebe que la entidad de certificación está en la lista de CA de confianza.


