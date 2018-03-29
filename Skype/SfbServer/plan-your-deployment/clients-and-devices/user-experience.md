---
title: Planear la experiencia de cliente de Skype Empresarial para sus usuarios
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Resumen: Conozca el nuevo Skype para los negocios y los pasos que puede seguir para preparar el entorno y los usuarios para la actualización, si utiliza Skype para los negocios en línea, Skype para Lync Server 2010, Lync Server 2013 o Business Server 2015.'
ms.openlocfilehash: 6ab79741a7a536e80beda0bc529351741136ea13
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-the-skype-for-business-client-experience-for-your-users"></a>Planear la experiencia de cliente de Skype Empresarial para sus usuarios
 
**Resumen:** Conozca el nuevo Skype para los negocios y los pasos que puede seguir para preparar el entorno y los usuarios para la actualización, si utiliza Skype para los negocios en línea, Skype para Lync Server 2010, Lync Server 2013 o Business Server 2015.
  
14 de abril de 2015 Office Update para Lync 2013 incluye el nuevo Skype para la interfaz de usuario de negocio. Esta actualización permite a los administradores controlar la apariencia del cliente y elegir si desea conservar la experiencia del cliente Lync 2013 o utilizar el Skype mejorada para la experiencia del cliente de negocios. El Skype para Business client eficazmente reemplaza al cliente Lync 2013 y agrega la capacidad de los administradores a elegir entre la experiencia del cliente Lync existente y el nuevo Skype para la experiencia del cliente de negocios. Para obtener información acerca de esta actualización, consulte [del 14 de abril de 2015 actualizar para Lync 2013 (Skype para empresas) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
El 12 de mayo de 2015 habrá otra actualización mensual de Office que incluye el Skype actualizado para cliente de empresa. Muchos clientes que no se hicieron aplicado la actualización tomará el 12 de mayo de abril actualización Office 2013. La información de este tema le ayudará a preparar a su organización, el entorno y sus usuarios para la actualización del cliente. Para que la transición sea fácil para los usuarios y equipos de asistencia, use la información de este tema como ayuda para decidir qué experiencia de cliente desea para los usuarios y, a continuación, realice los cambios en el entorno antes de implementar la actualización del cliente en la organización.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Preparar el entorno para el Skype para cliente de negocios](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de empresa 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>¿Qué experiencia de cliente desea para sus usuarios?
<a name="clientexperience"> </a>

Con el nuevo Skype para cliente de empresa, puede controlar qué experiencia de cliente los usuarios obtener, Lync o Skype para el negocio. La experiencia de cliente predeterminada depende de si está utilizando Lync o Skype para negocios locales o en línea. Si utiliza Skype para los negocios en línea (Lync Online) hoy con Office 365 ProPlus, Office 365 Business Premium u Office 2013, experimentar el Skype actualizado para Business client: inspirado en el aspecto de Skype: será la experiencia de usuario predeterminado. Si está utilizando Lync Server local hoy en día, la experiencia del cliente Lync será el predeterminado.
  
Puede configurar la experiencia de cliente que obtienen los usuarios mediante las directivas de cliente. Una directiva de cliente es un conjunto de opciones de configuración que se aplican a los usuarios cuando iniciar sesión en Lync o Skype para el negocio.
  
### <a name="skype-for-business-client-experience"></a>Experiencia de cliente de Skype Empresarial

Además de todas las características de Lync, Skype para empresas ofrece nuevas funciones con controles simplificados y los iconos que ya conoce de Skype. Algunas funciones nuevas de Skype para empresas sólo están disponibles con el nuevo Skype para la experiencia del cliente empresarial. Para obtener más información acerca de las nuevas características de Skype para empresas, consulte [Descubrir Skype para el negocio](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiencia de cliente Lync

La experiencia de cliente de Lync es muy similar a la experiencia de cliente de Lync 2013 con la que los usuarios ya están familiarizados, pero presenta algunos cambios que los usuarios deben conocer. Para ver la diferencia entre la experiencia del cliente de Lync y el cliente Lync 2013, consulte [¿por qué ver Skype para el negocio cuando utilizo Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) y los vínculos adicionales más adelante en este tema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar el entorno para el cliente de Skype Empresarial
<a name="usinglync"> </a>

Para que el entorno esté preparado para la actualización del cliente, debe realizar algunos cambios. Antes de empezar a realizar los cambios en la configuración de la experiencia del cliente, debe asegurarse de que está utilizando una versión de Skype para Business Server o Lync Server que admite la configuración de directiva de cliente.
  
Una vez que haya confirmado que está utilizando una versión de Skype para Business Server o Lync Server que admite la configuración de directiva para controlar la experiencia del cliente, debe configurar las opciones de directiva en el entorno. Los pasos específicos que debe seguir dependen de la versión de Skype para Business Server o Lync Server que está utilizando, y si los usuarios locales o en línea. 
  
Desea realizar estos cambios antes de la actualización de cliente se entrega a los usuarios para que puedan controlar la experiencia del cliente desde la primera vez que inicien el Skype para Business client. Las siguientes tablas se señala los pasos que debe seguir para configurar el entorno para la experiencia del cliente que desee para los usuarios.
  
|**Implementación**|**Skype para la experiencia del cliente de negocios**|**Experiencia del cliente Lync**|
|:-----|:-----|:-----|
|Skype Empresarial Online  <br/> |No hay pasos adicionales, solo debe implementar la compilación del cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Utilizar la experiencia del cliente Lync con Skype para los negocios en línea](user-experience.md#LyncwithSfBO) <br/> |
|Skype Empresarial Server 2015  <br/> |No hay pasos adicionales, solo debe implementar la compilación del cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Utilizar la experiencia del cliente Lync con Skype para Business Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 y Lync Server 2010  <br/> |[Utilizar la experiencia del cliente de Skype con Lync Server 2013 o en locales de Lync Server 2010](user-experience.md#SkypewithLynconprem) <br/> |[Utilizar la experiencia del cliente Lync con Lync Server 2013 o en locales de Lync Server 2010](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilizar la experiencia del cliente de Skype con Lync Server 2013 o en locales de Lync Server 2010
<a name="SkypewithLynconprem"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente Skype en una implementación local. Esta es la experiencia predeterminada para un entorno local.
  
 **Paso 1:** En primer lugar, asegúrese de que está ejecutando una versión de Lync Server que admite la configuración de directiva de cliente.
  
- **Lync Server 2013** - debe ejecutar el de diciembre de 2014 actualización acumulativa (5.0.8308.857) para Lync Server 2013 o una actualización posterior. Para obtener información, vea [versiones de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** : debe estar ejecutando el febrero de 2015 actualización acumulativa (4.0.7577.710) para Lync Server 2010 o una actualización posterior. Para obtener información, vea [versiones de Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
 **Paso 2:** A continuación, utilice una directiva de cliente para configurar la experiencia del cliente de Skype con el Skype para Business client. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente.
  
 **Opción 1:** Establecer la experiencia de cliente Skype con una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de su implementación, pero las directivas de nivel de usuario y de sitio tienen prioridad sobre la directiva global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opción 2:** Modificar una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia del cliente de Skype. Esto le permite asignar la experiencia del cliente Skype solo a aquellos usuarios que tienen asignada la directiva existente:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opción 3:** Crear una nueva directiva para asignar a los usuarios que incluye la configuración de la experiencia de cliente Skype. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor del parámetro  **Identity**:
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

A continuación, asigne la directiva a usuarios, usando el nombre de la directiva (el valor que ha usado para el parámetro **Identity**) como valor del parámetro **PolicyName**:
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Paso 3:** Después de haber configurado las directivas de cliente, implementar el Skype para Business client, compilación 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Utilizar la experiencia del cliente Lync con Lync Server 2013 o en locales de Lync Server 2010
<a name="LyncwithLynconprem"> </a>

Esto es la predeterminada cuando el Skype para cliente de negocios se implementa en una implementación de Lync Server local. No es necesario configurar directivas de cliente para usarla experiencia de cliente Lync, pero puede controlar el comportamiento de la primera ejecución del cliente. De forma predeterminada, la primera vez que los usuarios inician el Skype para cliente de negocios, la experiencia del cliente de Skype se utiliza y se muestra una notificación a los usuarios que solicita que reinicie el cliente para obtener la experiencia de cliente Lync. Puede configurar el entorno de modo que se muestre la experiencia de cliente Lync la primera vez que los usuarios inician el cliente y desactivar el tutorial de cliente modificando el registro del sistema en equipos cliente. Para conocer los pasos que necesita realizar antes de implementar el Skype para cliente de empresa, consulte uno de los siguientes temas:
  
- **Lync Server 2013**, consulte [Configurar el cliente experiencia con Skype para empresas Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** vea [Configure el cliente experiencia con Skype para el negocio en Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar la experiencia de cliente Lync con Skype Empresarial Server local
<a name="LyncwithSfBServer"> </a>

Siga los pasos de esta sección si desea configurar la experiencia del cliente Lync en un Skype local para la implementación de Business Server 2015.
  
Siga los pasos de esta sección si desea configurar la experiencia de cliente Skype en una implementación local. Esta es la experiencia predeterminada para un entorno local.
  
 **Paso 1:** En primer lugar, implementar Skype para Business Server 2015.
  
 **Paso 2:** A continuación, utilice una directiva de cliente para configurar la experiencia del cliente Lync con el Skype para Business client. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente.
  
 **Opción 1:** Establecer la experiencia de cliente Lync mediante una directiva global. Tenga en cuenta que la directiva global se aplica a todos los usuarios de la implementación, pero las directivas de nivel usuario y de sitio tienen prioridad sobre la directiva global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opción 2:** Modificar una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente Lync. Esto le permite asignar la experiencia de cliente Lync solo a aquellos usuarios que tienen asignada la directiva existente:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opción 3:** Crear una nueva directiva para asignar a los usuarios que incluye la configuración de la experiencia de cliente Lync. En primer lugar, cree la nueva directiva de cliente y proporcione el nombre de la directiva como valor de parámetro **Identity**:
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

A continuación, asigne la directiva a usuarios, usando el nombre de la directiva (el valor que ha usado para el parámetro **Identity**) como valor del parámetro **PolicyName**:
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Paso 3: opcional** : de manera predeterminada, la primera vez que los usuarios inician el Skype para el cliente de Business, la experiencia del cliente de Skype se utiliza y se muestra una notificación a los usuarios para pedirles que reinicie el cliente para obtener la experiencia de cliente Lync. Puede configurar su entorno para que la experiencia del cliente Lync se muestra la primera vez que inicie al cliente de los usuarios, así como el desactivar el tutorial cliente, modificando el registro del sistema en los equipos cliente. Para [Configurar el cliente experiencia con Skype para empresas](../../deploy/deploy-clients/configure-the-client-experience.md), consulte los pasos que debe realizar antes de implementar el Skype para el cliente de Business.
  
 **Paso 4:** Después de haber configurado las directivas de cliente, implementar el Skype para Business client, compilación 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar la experiencia de cliente Lync con Skype Empresarial en línea
<a name="LyncwithSfBO"> </a>

Siga los pasos de esta sección si va a configurar la experiencia del cliente de Lync y mediante Skype para los negocios en línea.
  
Si utiliza Skype para los negocios en línea, puede todavía utilizar la experiencia del cliente Lync con el Skype para cliente de negocios en su organización mediante PowerShell remoto para configurar las directivas de cliente. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente. Tenga en cuenta que los nombres de parámetro y de directiva son diferentes de la configuración que se utiliza para configurar la experiencia del cliente cuando se utiliza Skype para negocios o Lync Server local.
  
 **Opción 1:** Establecer la experiencia del cliente Lync mediante una directiva Global. Tenga en cuenta que las directivas de cliente y el sitio aplicadas a los usuarios tienen prioridad sobre una directiva Global.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 2:** Modificar una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente Lync. Esto le permite asignar la experiencia de cliente Lync solo a aquellos usuarios que tienen asignada la directiva existente:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 3:** Utilice una instancia de directiva personalizada que incluye la configuración de la experiencia del cliente Lync.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Después de haber configurado las directivas de cliente, implementar el Skype para Business client, compilación 4711.1002 (abril de 2015) o posterior.
  
Para obtener información detallada acerca de cómo configurar el cliente experiencia con Skype para los negocios en línea, incluidos los pasos acerca de cómo controlar la primera experiencia de ejecución y puede utilizar para configurar el entorno de secuencias de comandos de PowerShell, consulte [de conmutación entre el Skype para los negocios y las interfaces de usuario de cliente Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos que le ayudarán a preparar a su equipos de asistencia y a los usuarios finales para la actualización
<a name="support"> </a>

Para hacer que sea más fácil para usted y su organización preparar para la transición, tenemos muchos más recursos disponibles para ayudarle a planificar, educar y haga participar a los usuarios finales.
  
- [Vídeo: Introducción a Skype para empresas](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype para guías de inicio rápido de Business (descarga)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync es ahora Skype para empresas: Novedades](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype para empresas: Guía paso a paso para nuevos usuarios](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [¿Por qué se ve cuando utilizo Lync Skype para el negocio?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

