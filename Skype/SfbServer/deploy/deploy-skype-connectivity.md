---
title: Implementación de la conectividad Skype en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumen: obtenga información sobre cómo conectar Skype Empresarial Server con Skype consumidor. También se conoce como conectividad Skype.'
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671686"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implementación de la conectividad Skype en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo conectar Skype Empresarial Server con Skype consumidor. También se conoce como conectividad Skype.
  
En este artículo se describe la implementación de la conectividad de Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Introducción a la conectividad de Skype para profesionales de TI

Skype Conectividad proporciona a los usuarios Skype Empresarial la capacidad de buscar y agregar usuarios Skype. Skype Connectivity es una característica de Skype Empresarial que permite habilitar la federación y la búsqueda de directorios con Skype usuarios. Después de habilitar Skype Conectividad, los usuarios de Skype Empresarial podrán buscar y agregar usuarios Skype.
  
## <a name="skype-directory-search"></a>búsqueda de directorios de Skype

Skype funcionalidad de búsqueda de directorios proporciona a los usuarios Skype Empresarial la capacidad de buscar contactos Skype. La funcionalidad de búsqueda permite a los usuarios buscar mediante lo siguiente:
  
- **Buscar por nombre para mostrar, ejemplo "John Doe"** : esto podría devolver muchos resultados, por lo que es posible que no encuentre lo que está buscando.
    
- **Buscar por nombre para mostrar más ubicación, ejemplo "John Doe en Barcelona"** : esto limitará considerablemente los resultados de la búsqueda.
    
- **Buscar por correo electrónico, ejemplo "johndoe@outlook.com"** : esto debería devolver un resultado en la mayoría de los casos; que coincide exactamente con el correo electrónico especificado. Pero si el mismo correo electrónico está asociado a más de una cuenta, se pueden devolver varios resultados.
    
- **Buscar por número de teléfono, ejemplo "123-123-1234":** esto debería devolver un resultado en la mayoría de los casos; que coincide exactamente con el teléfono especificado. Teléfono número debe incluir el código de país (es decir, 1-xxx-yyy-zzzz). Si el mismo número de teléfono está asociado a más de una cuenta, se pueden devolver varios resultados.
    
- **Buscar por Skype Nombre, ejemplo "JohnDoe1456"**: si se encuentra coincidencia exacta, se devolverá como primer resultado. Se pueden devolver otras posibles coincidencias de "nombre".
    
    > [!NOTE]
    > Skype Directory Search debe poder comunicarse con las siguientes direcciones IP en el puerto 443: 104.40.75.246, 23.101.135.34 y 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implementación admitida para la búsqueda de directorios de Skype

En la tabla siguiente se describe la compatibilidad con la búsqueda de directorios de Skype.
  

|&nbsp;|Skype Empresarial Server front-end|Front-end de Lync Server 2013 (o anterior)|Comentarios|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Server Edge   |Compatible   |No se admite   |Skype Empresarial Server y Edge son requisitos previos para la búsqueda de directorios de Skype   |
|Skype Empresarial Server Edge + Lync Server 2013 Edge implementado en paralelo   |Compatible   |No se admite   |Skype el tráfico de búsqueda de directorios fluye a través de servidores perimetrales de Skype Empresarial Server. El tráfico de federación pasa por el perímetro configurado por el administrador. Por ejemplo, el administrador podría optar por seguir enviando tráfico de federación a través de servidores perimetrales de Lync Server 2013 que no admitirían Skype búsqueda de directorios.   |
|Perimetral de Lync Server 2013 (o anterior)   |No se admite   |No se admite   ||
   
> [!NOTE]
> El servicio de libreta de direcciones que se ejecuta en Skype Empresarial Server front-end encuentra edge por la existencia del puerto de búsqueda de Skype 4443 en el servidor perimetral. 
  
> [!NOTE]
> En caso de que un cliente tenga varios sitios en su implementación local y si ha implementado solo un Skype Empresarial Server servidor o grupo perimetral, el tráfico de búsqueda de todos los sitios pasará por el único servidor perimetral disponible. El administrador debe asegurarse de que los grupos de todos los sitios pueden acceder al servidor o grupo perimetral Skype Empresarial Server implementado. 
  
> [!NOTE]
> Skype servicio de grafos limitará las solicitudes de búsqueda de cualquier cliente local o Microsoft 365 o Office 365 si la tasa de solicitudes supera las 15 solicitudes por segundo. 
  
> [!NOTE]
> Para los clientes locales de gran empresa, los dominios deberán agregarse a una lista de permitidos con el servicio de búsqueda de Skype para permitir mayores tasas de solicitudes.
  
> [!NOTE]
> Skype Empresarial Server limitará las solicitudes entrantes, si hay demasiadas solicitudes pendientes en la cola. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Implementación de la conectividad de Skype para Skype Empresarial Online

Skype Conectividad también es una característica de Skype Empresarial Online, que forma parte de Microsoft 365 y Office 365. Puede habilitar la característica conectividad de Skype desde el Centro de administración de Skype Empresarial en el Centro de administración de Microsoft 365.
  
Para Microsoft 365 mediana empresa, Office 365 Enterprise, Microsoft 365 Educación y Office 365 para government: inicie sesión en el Centro de administración de Microsoft 365 y vaya al Centro de administración de Skype Empresarial. Vaya a Comunicaciones externas. En Proveedores de servicios de mensajería instantánea pública, haga clic en Habilitar. Si desea controlar el acceso de usuarios individuales a Skype Conectividad, puede hacerlo editando la configuración de comunicaciones externas de los usuarios individuales.
  
Para Office 365 Pequeña Empresa Premium: inicie sesión en Office 365 y vaya a Administración \> Service Configuración \> Mensajería instantánea, reuniones y conferencias. Active Comunicaciones externas. El conmutador Comunicaciones externas activa la conectividad Skype y las comunicaciones con otras organizaciones que usan Skype Empresarial.
  
Para obtener más información sobre Skype Empresarial administración en línea, consulte:
  
- [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Qué probar si no puede Skype Empresarial de mensajería instantánea ni Skype contactos externos](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Agregar un contacto en Skype Empresarial](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: configuración de Skype Empresarial para usuarios individuales](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implementación de la conectividad de Skype para Skype Empresarial Server

Skype Empresarial Server usa la arquitectura de acceso de federación para admitir la conectividad con Skype. Esta conectividad permite a los usuarios de Skype Empresarial Server agregar Skype. Skype clientes también pueden agregar usuarios Skype Empresarial a su lista de contactos. En función de las directivas establecidas administrativamente en Skype Empresarial Server los usuarios podrán comunicarse mediante mensajería instantánea, ver la presencia del otro e iniciar llamadas de audio y vídeo. Skype conectividad también es una característica de Skype Empresarial Online y se puede habilitar para Skype Empresarial clientes en línea desde el Centro de administración de Skype Empresarial dentro de la Centro de administración de Microsoft 365.
  
> [!NOTE]
> Si Skype Empresarial Server ya está configurado para conectarse con Windows Messenger mediante la conectividad de mensajería instantánea pública (PIC), la implementación ya está configurada para Skype conectividad. El único cambio que puede considerar es cambiar el nombre de la entrada PIC de Messenger existente como Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>El sitio de aprovisionamiento de conectividad de mensajería instantánea pública Skype Empresarial Server ya no está disponible

El sitio que se usó anteriormente para aprovisionar manualmente la federación entre Skype Empresarial implementaciones locales y Skype ya no es necesario y se cerrará el 15/8/2019. La federación con Skype ahora usa la detección de asociados federados, que es el mismo mecanismo necesario para la federación con Skype Empresarial Online.

La comunicación entre cualquier implementación de Skype Empresarial local y los usuarios Skype a través de la infraestructura de mensajería instantánea pública existente ahora requiere que la configuración del servidor perimetral local sea compatible con Skype Empresarial Online.

> [!NOTE]
> La mayoría de los clientes no necesitan ninguna acción, incluidas todas las implementaciones que se federan con Skype Empresarial Online.
  
Las implementaciones locales son necesarias para publicar un registro SRV de DNS de federación para cada dominio que hospedan. Las instrucciones están disponibles en [el planeamiento de DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Cada dominio debe resolverse mediante la consulta SRV de DNS en un FQDN de servidor perimetral que satisfaga una coincidencia de sufijos de nivel superior del dominio. Por ejemplo, considere el dominio "contoso.com":

|**FQDN válidos**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |En cada caso, el FQDN exacto debe estar presente en el SN o la SAN del certificado externo instalado en el servidor perimetral.   |
|access.contoso.com   ||
|**FQDN no válidos**|**Motivo**|
|sip.contoso-edge.com   |No es una coincidencia de sufijo.  |
|sip.it.contoso.com   |No es una coincidencia de sufijo de nivel superior.   |

Encontrará más instrucciones sobre certificados externos en [Planeamiento de certificados](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Preguntas frecuentes

**¿Por qué se cierra el sitio web de aprovisionamiento?**
El mecanismo de aprovisionamiento de MI pública (PIC) (pic.lync.com) que se implementó en 2006 ya no se puede atender y se cerrará el 15/8/2019. En su lugar, la federación de mensajería instantánea pública asumirá el mismo modelo de federación usado por Skype Empresarial Online, conocido como "detección de asociados", por el que una implementación local es reconocible públicamente por sus registros SRV de DNS de federación.

**¿Significa este cambio que la federación de mensajería instantánea pública está en desuso?**
No. La federación de mensajería instantánea pública seguirá siendo compatible durante muchos años, probablemente hasta que el Skype Empresarial producto local llegue al final de su vida útil.

**Nuestra empresa tiene una relación híbrida (espacio de direcciones compartidas) con Skype Empresarial Online, ¿nos afecta?**
No, dado que ya está federando con Skype Empresarial Online, este cambio no le afectará.
 
**¿Significa este cambio que nuestra empresa tiene que habilitar la federación con Skype Empresarial Online?**
No. Si la configuración del proxy del servidor perimetral no habilita la federación con el proveedor de hospedaje Skype Empresarial Online (sipfed.online.lync.com), este cambio no afectará a eso. Sin embargo, los mismos requisitos de DNS y certificado que se aplican a la federación con Skype Empresarial Online ahora también se aplican a la federación con Skype usuarios.
 
**Nuestra empresa es grande y no puede cambiar su configuración perimetral debido a motivos normativos, de cumplimiento, etc... ¿Qué podemos hacer?**
Cualquier organización local que no pueda cambiar la configuración del servidor perimetral según lo especificado debe ponerse en contacto con el soporte técnico del producto lo antes posible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitación de la conectividad de federación y mensajería instantánea pública (PIC)

Ahora céntrese en el entorno Skype Empresarial Server y las tareas administrativas necesarias para configurar la conectividad Skype. En esta sección, se supone que el administrador ha implementado Skype Empresarial Server y configurado el acceso externo, también conocido como servidores perimetrales. 
  
Hay tres pasos principales necesarios para habilitar la federación y PIC. Son:
  
1. Configuración de federación y PIC
    
2. Configuración de al menos una directiva para admitir el acceso de usuarios federados
    
3. Configuración del proveedor Skype PIC
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar federación y PIC

La federación es necesaria para permitir que Skype usuarios se comuniquen con Skype Empresarial usuarios de su organización. La conectividad de mensajería instantánea pública (PIC) es una clase de federación y debe configurarse para permitir que los usuarios de Skype Empresarial se comuniquen con Skype usuarios. La federación y pic se configuran mediante el Skype Empresarial Server Panel de control.
  
> [!NOTE]
> La federación PIC ya no es compatible con las versiones de producto anteriores a Lync Server 2010 (Live Communication Server, Office Communications Server). Las plataformas admitidas para la federación PIC incluyen Skype Empresarial Server, Lync Server 2013 y Lync Server 2010. 
  
La federación es necesaria para permitir que Skype usuarios se comuniquen con Skype Empresarial usuarios de su organización. La conectividad de mensajería instantánea pública (PIC) es una clase de federación y debe configurarse para permitir que los usuarios de Skype Empresarial Server se comuniquen con Skype usuarios. La federación y PIC se configuran mediante el cuadro de diálogo Configuración perimetral de la Skype Empresarial Server Panel de control, como se muestra en la ilustración.
  
![Definir nuevo grupo de servidores perimetrales.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Los atributos EnableSkypeIdRouting y EnableSkypeDirectorySearch deben establecerse en true en la configuración del proveedor público (consulte las instrucciones posteriores) para que la búsqueda funcione. 
  
Esto completa las tareas administrativas que se deben realizar en el servidor. Ahora está configurado para la conectividad Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurar al menos una directiva para admitir el acceso de usuarios federados

Con el Skype Empresarial Server Panel de control, un administrador debe configurar una o varias directivas de acceso de usuarios externos para controlar si Skype usuarios pueden colaborar con usuarios internos de Skype Empresarial Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configuración del proveedor Skype PIC

Con el Shell de administración de Skype Empresarial Server, un administrador debe configurar la directiva de cliente de Skype Empresarial para mostrar Skype como un proveedor PIC adicional. 
  
> [!NOTE]
> Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea pública (PIC) no pueden participar en mensajería instantánea o conferencias en su organización hasta que también configure al menos una directiva (paso 2, anterior en este procedimiento) para admitir la conectividad de mensajería instantánea pública. 
  
Para las instalaciones nuevas, puede configurar la conectividad de Skype habilitando un proveedor público de Skype mediante el Skype Empresarial Server Panel de control como se muestra en la ilustración.
  
![Proveedores federados SIP.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar la conectividad Skype al actualizar a Skype Empresarial Server debe quitar y volver a agregar el proveedor público de Skype existente. 
  
La configuración de la conectividad Skype también se puede realizar mediante PowerShell. Para configurar la conectividad Skype mediante PowerShell:
  
1. En un servidor front-end Skype Empresarial Server, abra el Shell de administración de Skype Empresarial Server.
    
2. Ejecute los dos comandos siguientes:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si aún no tiene un proveedor PIC en su entorno y está creando un nuevo proveedor DE PIC, no es necesario ejecutar el cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    ¿Qué hacen los parámetros menos obvios?
    
   - ProxyFqdn: ubicación de Skype borde de federación (propiedad o mantenimiento de Microsoft)
    
   - IconURL: icono utilizado por el cliente de Lync &amp; Skype Empresarial para identificar visualmente los contactos Skype
    
   - NameDecorationRoutingDomain y NameDecorationExcludedDomainList: al establecer esta opción, los usuarios pueden escribir Skype MSA de los usuarios sin necesidad de saber sobre la "decoración" de dominios que no son de Microsoft con "msn.com". Esto elimina la necesidad de escribir "user(contoso.com)@msn.com" para todos los dominios que NO están en ExcludedDomainList. El cliente SfB dará formato automáticamente a la MSA si el dominio NO está en la lista Excluidos. Hemos agregado los dominios de cuenta microsoft más comunes a la lista excluida.
    
     > [!NOTE]
     > El proveedor público debe quitarse y agregarse nuevo si se realizan cambios. No se permite ningún cambio local. 
  
     > [!NOTE]
     > Agregado en el cliente de escritorio lync de Lync Server 2013 CU5 &amp; en Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos Skype necesarios para "decorar" dominios que no son de Microsoft para identificarlos y enrutarlos a Skype (el formato de: user(contoso.com)@msn.com). Esta nueva configuración permitirá el formato automático de la dirección que escriba el usuario en el cuadro de diálogo "Agregar contacto de Skype" con NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios de NameDecorationExcludedDomainList (actualmente podemos admitir msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Desde un Skype Empresarial los usuarios cliente ahora pueden buscar y agregar un usuario Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matriz de clientes e interoperabilidad

En la tabla siguiente se describe el estado de interoperabilidad entre la versión más reciente de Skype consumidor y la versión más reciente de Skype Empresarial.
  

|Clientes de Skype|Agregar contactos, mensajería instantánea, presencia, audio y videollamadas|Comentario|
|:-----|:-----|:-----|
|escritorio de Skype Windows   |7.6 o superior, Windows XP y versiones posteriores   |**NUEVO**: Se ha agregado compatibilidad con Windows Skype cliente que se ejecuta en Windows XP y Windows Vista **(requiere la versión de cliente más reciente 7.26 o posterior)**  |
|Skype Mobile: Android Teléfono y tableta   |6.19 o posterior, ejecutando Android versión 4.0.3 o posterior del sistema operativo   |Es posible que los dispositivos de especificaciones bajas no admitan videollamadas.   |
|Skype Mobile: iOS   |6.11 o superior, en IOS 7 o superior   |No se admiten iPhone 4 y versiones anteriores, iPod 4.ª generación y versiones anteriores, iPad primera generación   |
|Skype Mac   |7.19 o superior, en Mac OS X 10.9 (Mavericks) o superior   |Requiere Mac OSX 10.9 o superior   |
|Skype Aplicación universal de Windows (Windows 10) escritorio y móvil   |Windows 10 (actualización de Redstone 1 o posterior)   |Windows aplicación universal recibirá la actualización en otoño de 2016, lo que agrega compatibilidad con la interoperabilidad   |
   
En la tabla siguiente se describe el estado de interoperabilidad entre la versión más reciente de Skype Empresarial y la versión más reciente de Skype consumidor. 
  
|Cliente|Skype búsqueda de directorios y agregar contactos|Skype A/V, interoperabilidad de MI|
|:-----|:-----|:-----|
|Skype for Business   |Sí   |Sí   |
|Skype Empresarial en Mac   |Puede agregar (sin búsqueda)   |Sí   |
|Lync Desktop 2013   |Puede agregar (sin búsqueda)   |Sí   |
|Lync Web App: en línea y local   |N/D   |N/D   |
|Lync Mobile: Windows Phone   |Próximamente.   |Sí   |
|Lync Mobile: Android   |Próximamente.   |Sí   |
|Lync Mobile: iOS   |Próximamente.   |Sí   |
|Sistema Lync Room   |Próximamente.   |Sí   |
|Lync Modern App (Win 8.1)   |Sí   |Sí   |
|Lync Mac 2011   |Puede agregar (sin búsqueda)   |Sí   |
|Lync Desktop 2010   |Puede agregar (sin búsqueda)   |Sí   |
|Lync Phone Edition   |N/D   |N/D   |
|Operador de Lync   |N/D   |N/D   |
   
