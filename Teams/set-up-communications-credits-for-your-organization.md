---
title: Configurar Créditos de comunicaciones para su organización
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 426ca88cb25aad988960add812595f89eed17595
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838030"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurar Créditos de comunicaciones para su organización

Debe configurar créditos de comunicaciones si pretende usar números gratuitos con Skype for Business y Microsoft Teams. Además, le recomendamos que configure créditos de comunicaciones para los planes de llamadas (nacionales o internacionales) y los usuarios de las conferencias de audio que necesiten poder marcar a **cualquier destino**. Se incluyen muchos países o regiones, pero es posible que algunos destinos no se incluyan en su plan de llamadas o suscripciones de audioconferencia. Si no configura la facturación de créditos de comunicaciones y asigna una licencia de **créditos de comunicaciones** a los usuarios y los minutos se agotan para su organización (según el plan de llamadas o el plan de audioconferencia de su país o región), esos usuarios no podrán hacer llamadas ni llamar desde reuniones de audioconferencia. Puede obtener más información, entre las que se incluyen los importes de financiamiento recomendados, leyendo [¿Qué son los créditos de comunicaciones?](what-are-communications-credits.md)
  
> [!NOTE]
> Para saber cuánto cuesta, [consulte aquí las tarifas](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Paso 1: asignar una licencia de conferencia de audio o plan de llamadas a los usuarios

Al registrarse, obtendrás un determinado número de minutos, en función de tu país o región. Puedes ver la cantidad de minutos que recibirás [aquí](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)para buscar el país o la región. Después de usar esos minutos, las llamadas se desconectarán. Para evitar que esto suceda, debe configurar créditos de comunicaciones.
  
Para ello, debe **asignar una licencia de audioconferencia o de sistema telefónico** a los usuarios.
  
- Asigne una licencia de **audioconferencia** a sus usuarios. Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md).
    
    Después de asignar esta licencia, tendrá que configurar audioconferencia. Para obtener instrucciones paso a paso, consulte [probar o comprar audioconferencia en Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).
    
- Asigne un **sistema telefónico** y una licencia de plan de llamadas **nacionales o nacionales e internacionales** a los usuarios. Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md).
    
    > [!NOTE]
    > Aunque no es necesario para el crédito de las comunicaciones, aún tiene que asignar un **plan de llamadas nacionales** o una licencia de **plan de llamadas nacionales e internacionales** .
  
    Después de asignar estas licencias, tendrá que obtener sus números de teléfono para la organización y asignarlos a los miembros de su organización. Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](set-up-calling-plans.md).
    
Para obtener más información, consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Paso 2: configurar créditos de comunicaciones para su organización

1. Inicie sesión en el nuevo portal de Office 365 con su cuenta profesional o educativa.
    
2. En el centro de navegación izquierdo del centro de administración de Microsoft 365, vaya a**** > **suscripciones**de **facturación** > agregar suscripciones.

3. Expanda **suscripciones de complementos**y, a continuación, seleccione **créditos** > de comunicaciones**comprar ahora**.
    
4. En la página de suscripción de **crédito de comunicaciones** , rellene la información y, a continuación, haga clic en **siguiente**:
    
   - **Agregar fondos** Escribe la cantidad que deseas añadir a tu cuenta. Si no habilita la recarga automática, una vez que se agoten estos fondos, se interrumpirán las llamadas que estén habilitadas con el uso de créditos de comunicaciones (como un servicio entrante). Para evitar tener que rellenar manualmente el saldo de tu crédito de comunicaciones cada vez que tu saldo alcance 0 (cero), te recomendamos que habilites la característica de recarga automática.
    
   - **Recarga automática** Si habilita la recarga automática, ls cuenta se rellenará automáticamente cuando el saldo esté por debajo del umbral que establezca.
    
     Le recomendamos que use la configuración de la **recarga automática** para evitar interrupciones en el servicio si su saldo del crédito de comunicaciones alcanza el valor 0 (cero). Se le enviará un correo electrónico cuando se recarguen las transacciones, cuando se produzcan errores en las transacciones de recarga (como una tarjeta de crédito vencida) y cuando el saldo de sus créditos de comunicaciones alcance 0 (cero).
    
   - **Cantidad de recarga** Escribe la cantidad en el cuadro de **recarga con** que deseas añadir a tu cuenta una vez que llegue a la cantidad de activación a continuación.
    
   - **Desencadenar monto** Escribe la cantidad en **cuando el saldo es inferior** a la casilla que se usará para ' *desencadenar* ' la recarga automática. Una vez que tu saldo sea inferior a esta cantidad, el monto de recarga se añadirá automáticamente a tu cuenta.

      > [!NOTE]
     > Los fondos se aplicarán únicamente a los créditos de comunicaciones de las tarifas publicadas de Microsoft cuando se usen los servicios. Los fondos que no se usen en 12 meses desde la fecha de compra se perderán. 
     > 
     > La facturación mensual para créditos de comunicación solo se aplicará si el fondo asignado se ha usado, para aprender a comprobar el uso mensual, leer el [Informe de uso de RTC de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. Escriba la información de pago y haga clic en **Realizar pedido**.
    >[!IMPORTANT]
    >Si es un cliente de licencias por volumen, puede elegir su número de enterprise agreement para el pago. Si tiene varios números, podrá seleccionar qué enterprise agreement prefiere usar para dicho pago. También podrá especificar un número de pedido de compra que asociar al número del enterprise agreement (si procede).
    
Cada organización tendrá un uso diferente del volumen de la planificación de llamadas y las tarifas a tener en cuenta. You will need to get this type of usage data from your current service provider. Las organizaciones que ya usan Skype empresarial online ya que su proveedor de servicios pueden obtener datos de uso si lo revisan en el **Centro** > de administración de Skype empresarial**informes** > **detalles de uso de RTC** .
  
Al configurar créditos de comunicaciones, tendrá que investigar el uso de las llamadas de su organización para determinar los montos que necesita. Puede obtener la información del uso de llamadas en el informe **Detalles de uso de RTC**. Este informe le permite exportar los registros de datos de llamadas a Excel si necesita almacenar los datos o crear informes personalizados. Para obtener más información sobre cómo ver el uso, lea el [Informe de uso de RTC de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Paso 3: asignar una licencia de créditos de comunicaciones a los usuarios

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. En el centro de navegación izquierdo del centro de administración de Microsoft 365, **vaya a** > usuarios**activos**y, a continuación, seleccione un usuario o usuarios de la lista.
    
3. En el panel de acciones, en **Licencias de productos**, haga clic en **Editar**.
    
4. En la página **licencias de producto** , active la opción créditos de **comunicaciones** en **activado** para asignar esta licencia y, a continuación, haga clic en **Guardar**.
    
    > [!NOTE]
    > Aunque tenga usuarios a los que se les haya asignado una licencia de **Enterprise E5** , le recomendamos que lo haga.
  
## <a name="want-to-know-about-plans-and-pricing"></a>¿Desea obtener información acerca de los planes y los precios?

Para ver los planes y los precios, visite uno de los siguientes vínculos:
  
- [Planes de llamadas](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Planes de audioconferencia](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Planes de sistemas telefónicos](https://go.microsoft.com/fwlink/?LinkId=799763)
    
También puede ver información [iniciando sesión en el centro de administración de Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) y yendo a**suscripciones** > de **facturación** > para**Agregar suscripciones**.
  
Para ver una tabla con las licencias que necesitará para cada característica, consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Temas relacionados

- [Configurar Skype Empresarial Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurar el Correo de voz en la nube. Ayuda para el administrador](set-up-phone-system-voicemail.md)
    
- [Configurar planes de llamada](set-up-calling-plans.md) y [Planes de llamada de Office 365](calling-plans-for-office-365.md)
    
- [Agregar fondos y administrar los créditos de comunicaciones](add-funds-and-manage-communications-credits.md)
    
  
 
