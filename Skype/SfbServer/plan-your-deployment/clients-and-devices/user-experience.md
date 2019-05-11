---
title: Planear la Skype para la experiencia del cliente empresarial 2015 para los usuarios
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Resumen: Información sobre el nuevo Skype para la empresa y los pasos que puede realizar para preparar su entorno y a los usuarios para la actualización, si está utilizando de Skype para profesionales en línea, Skype para Business Server 2019, Skype para Business Server 2015, Lync Server 2013, o Lync Server 2010.'
ms.openlocfilehash: 9b6f7bbe5fdeecc8a017b973e7b77912819da789
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886476"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planear la Skype para la experiencia del cliente empresarial 2015 para los usuarios
 
**Resumen:** Obtenga información sobre el nuevo Skype para profesionales y los pasos que puede realizar para preparar su entorno y a los usuarios para la actualización, si está utilizando de Skype para profesionales en línea, Skype para Business Server 2019, Skype para Business Server 2015, Lync Server 2013 o Lync Server 2010.
  
14 de abril de 2015 Office Update para Lync 2013 incluye el nuevo Skype para la interfaz de usuario de negocio. Esta actualización permite a los administradores controlar la apariencia del cliente y elija si desea conservar la experiencia del cliente Lync 2013 o usar el Skype mejorada para la experiencia del cliente empresarial. El Skype para clientes empresariales eficazmente reemplaza al cliente Lync 2013 y agrega la capacidad de los administradores elegir entre la experiencia del cliente Lync existente y el nuevo Skype para la experiencia del cliente empresarial. Para obtener información acerca de esta actualización, vea [actualizar el 14 de abril de 2015 para Lync 2013 (Skype para la empresa) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
En el 12 de mayo de 2015 será otra actualización mensual desde Office que incluye la Skype actualizada para clientes empresariales. Muchos clientes que no se aplicó la actualización se encargará de recoger el 12 de mayo de abril de actualización para Office 2013. La información de este tema le ayudará a preparar a su organización, el entorno y sus usuarios para la actualización del cliente. Para que la transición sea fácil para los usuarios y equipos de asistencia, use la información de este tema como ayuda para decidir qué experiencia de cliente desea para los usuarios y, a continuación, realice los cambios en el entorno antes de implementar la actualización del cliente en la organización.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Preparar el entorno para el cliente de Skype Empresarial](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de 2016 empresarial. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>¿Qué experiencia de cliente desea para sus usuarios?
<a name="clientexperience"> </a>

Con el nuevo Skype para cliente empresarial, puede controlar qué experiencia del cliente a los usuarios obtienen, Lync o Skype para la empresa. La experiencia del cliente predeterminado depende de si está utilizando Lync o Skype para empresarial local o en línea. Si usa Skype para profesionales en línea (Lync Online) hoy mismo con Office 365 ProPlus, Office 365 Business Premium o Office 2013, experiencia la Skype actualizada para cliente empresarial: inspiración por la apariencia de Skype: será la experiencia del usuario de forma predeterminada. Si usa Lync Server local hoy en día, la experiencia del cliente Lync será el predeterminado.
  
Puede configurar la experiencia de cliente que obtienen los usuarios mediante las directivas de cliente. Una directiva de cliente es un conjunto de opciones de configuración que se aplican a los usuarios cuando iniciar sesión en Lync o Skype para la empresa.
  
### <a name="skype-for-business-client-experience"></a>Experiencia de cliente de Skype Empresarial

Además de todas las características de Lync, Skype para la empresa proporciona nuevas características con controles simplificados y los iconos que ya conoce de Skype. Algunas características nuevas de Skype para la empresa sólo están disponibles con el nuevo Skype para la experiencia del cliente empresarial. Para obtener más información acerca de las nuevas características de Skype para la empresa, vea [Detectar Skype para la empresa](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiencia de cliente Lync

La experiencia de cliente de Lync es muy similar a la experiencia de cliente de Lync 2013 con la que los usuarios ya están familiarizados, pero presenta algunos cambios que los usuarios deben conocer. Para ver qué es diferente entre la experiencia del cliente Lync y el cliente de Lync 2013, consulte [¿por qué ver Skype para la empresa cuando estoy usando Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) y los vínculos adicionales más adelante en este tema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar el entorno para el cliente de Skype Empresarial
<a name="usinglync"> </a>

Para que el entorno esté preparado para la actualización del cliente, debe realizar algunos cambios. Antes de empezar a realizar cualquier cambio en la configuración de la experiencia del cliente, primero debe asegurarse de que está usando una versión de Skype para Business Server o Lync Server que es compatible con la configuración de directiva de cliente.
  
Una vez que haya confirmado que está utilizando una versión de Skype para Business Server o Lync Server que es compatible con la configuración de directiva para controlar la experiencia del cliente, debe configurar la configuración de directiva en el entorno. Los pasos específicos que debe seguir dependen de la versión de Skype para Business Server o Lync Server que esté utilizando y, si los usuarios se encuentran en local o en línea. 
  
Desea realizar estos cambios antes de la actualización de cliente se entrega a los usuarios para que pueda controlar la experiencia del cliente desde la primera vez que inicien la Skype para clientes empresariales. En las tablas siguientes se apunta a los pasos que debe seguir para configurar el entorno para la experiencia del cliente que desee para los usuarios.
  
|**Deployment**|**Experiencia de cliente de Skype Empresarial**|**Experiencia de cliente Lync**|
|:-----|:-----|:-----|
|Skype Empresarial Online  <br/> |No hay pasos adicionales, solo debe implementar la compilación del cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente Lync con Skype Empresarial en línea](user-experience.md#LyncwithSfBO) <br/> |
|Skype Empresarial Server 2015  <br/> |No hay pasos adicionales, solo debe implementar la compilación del cliente 4711.1002 (abril de 2015) o posterior.  <br/> |[Usar la experiencia de cliente Lync con Skype Empresarial Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 y Lync Server 2010  <br/> |[Usar la experiencia del cliente de Skype con Lync Server 2013 o local de Lync Server 2010](user-experience.md#SkypewithLynconprem) <br/> |[Usar la experiencia del cliente Lync con Lync Server 2013 o local de Lync Server 2010](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia del cliente de Skype con Lync Server 2013 o local de Lync Server 2010
<a name="SkypewithLynconprem"> </a>

Siga los pasos de esta sección si desea configurar la experiencia de cliente Skype en una implementación local. Esta es la experiencia predeterminada para un entorno local.
  
 **Paso 1:** En primer lugar, asegúrese de que está ejecutando una versión de Lync Server que es compatible con la configuración de directiva de cliente.
  
- **Lync Server 2013** - debe ejecutar el de diciembre de 2014 actualización acumulativa (5.0.8308.857) para Lync Server 2013 o una actualización posterior. Para obtener información, vea [actualizaciones de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** - debe ejecutar el de febrero de 2015 actualización acumulativa (4.0.7577.710) para Lync Server 2010 o una actualización posterior. Para obtener información, vea [actualizaciones de Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Paso 2:** A continuación, utilice una directiva de cliente para establecer la experiencia del cliente de Skype con el Skype para clientes empresariales. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente.
  
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

 **Paso 3:** Una vez que ha configurado las directivas de cliente, implementar el Skype para cliente empresarial, compilación 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar la experiencia del cliente Lync con Lync Server 2013 o local de Lync Server 2010
<a name="LyncwithLynconprem"> </a>

Esto es la experiencia predeterminada cuando se implementa el Skype para clientes empresariales en una implementación de Lync Server local. No es necesario configurar directivas de cliente para usarla experiencia de cliente Lync, pero puede controlar el comportamiento de la primera ejecución del cliente. De forma predeterminada, la primera vez que los usuarios inician la Skype para clientes empresariales, se usa la experiencia del cliente Skype y se mostrará una notificación a los usuarios que solicita que reinicie el cliente para obtener la experiencia del cliente Lync. Puede configurar el entorno de modo que se muestre la experiencia de cliente Lync la primera vez que los usuarios inician el cliente y desactivar el tutorial de cliente modificando el registro del sistema en equipos cliente. Para los pasos que necesita realizar antes de implementar el Skype para cliente de negocio, consulte uno de los siguientes temas:
  
- **Lync Server 2013**, vea [Configurar el cliente de experiencia con Skype para la empresa en Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** vea [Configurar el cliente de experiencia con Skype para la empresa en Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar la experiencia de cliente Lync con Skype Empresarial Server local
<a name="LyncwithSfBServer"> </a>

Siga los pasos descritos en esta sección si va a configurar la experiencia del cliente Lync en un Skype local para la implementación de Business Server.
  
Siga los pasos de esta sección si desea configurar la experiencia de cliente Skype en una implementación local. Esta es la experiencia predeterminada para un entorno local.
  
 **Paso 1:** En primer lugar, implemente Skype para Business Server.
  
 **Paso 2:** A continuación, utilice una directiva de cliente para establecer la experiencia del cliente Lync con la Skype para clientes empresariales. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente.
  
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

 **Paso 3: opcional** : de forma predeterminada, la primera vez que los usuarios inician la Skype para clientes empresariales, se usa la experiencia del cliente Skype y se mostrará una notificación a los usuarios para pedirles que reinicie el cliente para obtener la experiencia del cliente Lync. Puede configurar el entorno para que la experiencia del cliente Lync se muestre la primera vez que inicie al cliente de los usuarios, así como el desactivar el tutorial de cliente, mediante la modificación del registro del sistema en los equipos cliente. Para los pasos que necesarios para llevar a cabo antes de implementar el Skype para clientes empresariales, vea [Configurar el cliente de experiencia con Skype para la empresa](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Paso 4:** Una vez que ha configurado las directivas de cliente, implementar el Skype para cliente empresarial, compilación 4711.1002 (abril de 2015) o posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar la experiencia de cliente Lync con Skype Empresarial en línea
<a name="LyncwithSfBO"> </a>

Siga los pasos descritos en esta sección si va a configurar la experiencia del cliente Lync y usando Skype para profesionales en línea.
  
Si usa Skype para profesionales en línea, puede aún usar la experiencia del cliente Lync con la Skype para clientes empresariales de la organización mediante PowerShell remoto para configurar las directivas de cliente. Hay **3 opciones** para usar una directiva de cliente para establecer la experiencia de cliente. Tenga en cuenta que los nombres de directiva y el parámetro son diferentes de la configuración que se utiliza para configurar la experiencia del cliente cuando se usa Skype para empresariales o de Lync Server local.
  
 **Opción 1:** Establecer la experiencia del cliente Lync mediante una directiva Global. Tenga en cuenta que las directivas de cliente y el sitio aplicadas a los usuarios tienen prioridad sobre una directiva Global.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 2:** Modificar una directiva de cliente existente que está usando en su entorno para incluir la configuración para habilitar la experiencia de cliente Lync. Esto le permite asignar la experiencia de cliente Lync solo a aquellos usuarios que tienen asignada la directiva existente:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opción 3:** Usar una instancia de directiva personalizada que incluye la configuración de la experiencia del cliente Lync.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Una vez que ha configurado las directivas de cliente, implementar el Skype para cliente empresarial, compilación 4711.1002 (abril de 2015) o posterior.
  
Para obtener información detallada acerca de cómo configurar el cliente de experiencia con Skype para profesionales en línea, incluidos los pasos sobre cómo controlar la primera experiencia de ejecución y scripts de PowerShell que puede usar para configurar el entorno, vea el tema [de conmutación entre el Skype para profesionales y las interfaces de usuario de cliente de Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos que le ayudarán a preparar a su equipos de asistencia y a los usuarios finales para la actualización
<a name="support"> </a>

Para hacer que sea más fácil para usted y su organización preparar para la transición, tenemos muchos recursos adicionales disponibles que le ayudarán a planear, enseñar y contratar a los usuarios finales.
  
- [Vídeo: Presentación de Skype para la empresa](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype para guías de inicio rápido de Business (descarga)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync es ahora Skype para la empresa, vea Novedades](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype para la empresa: una guía paso a paso para nuevos usuarios](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [¿Por qué ver Skype para la empresa cuando estoy usando Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

