---
title: 'Programa de fin de vida para la integración de Skype Empresarial con proveedores de audioconferencias de terceros '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: El 31 de julio de 2021, el programa de fin de vida terminará con la integración de Skype Empresarial con proveedores de servicios de audioconferencia (ACP de terceros).
ms.openlocfilehash: 5b49bf573ad79cbdacbc538a0ef67faf1b2b634e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164459"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Programa de fin de vida para la integración de Skype Empresarial con proveedores de audioconferencias de terceros 

Microsoft ha anunciado el inicio del programa de fin de vida para la integración de Skype Empresarial con proveedores de servicios de audioconferencia (ACP) de terceros. 

El programa de fin de vida finalizará el 31 de julio de 2021. Cuando concluya el programa, la integración de Skype Empresarial con proveedores de audioconferencias de terceros dejará de funcionar y se observarán los siguientes cambios en esa fecha (31 de julio de 2021):

- Los participantes que intenten unirse a una reunión de Skype Empresarial a través de números de acceso telefónico proporcionados por un servicio ACP de terceros ya no estarán conectados a la reunión de Skype Empresarial.
 
- Los usuarios habilitados para un servicio ACP de terceros ya no tendrán su información de acceso telefónico en las nuevas invitaciones a reuniones de Skype Empresarial.

Como parte del anuncio del inicio del programa de fin de vida, el siguiente cambio ha tenido efecto y seguirá en su lugar hasta la conclusión del programa de fin de vida: 

- Los clientes sin usuarios de Skype Empresarial configurados para usar un servicio ACP de terceros no podrán configurar los usuarios para que usen un servicio ACP de terceros.

- Existing customers with Skype for Business users configured to use a third-party ACP service will continue to be able to add new users for the duration of the end of life period. Tenga en cuenta que no recomendamos configurar usuarios adicionales de Skype Empresarial para usar un servicio ACP de terceros, ya que los cambios que tendrán efecto el 31 de julio de 2021 también se aplicarán a ellos.

## <a name="preparing-for-this-change"></a>Prepararse para este cambio

Para prepararse para este cambio, animamos a las organizaciones afectadas a notificar a sus usuarios habilitados sobre esta actualización planeada antes del 31 de julio de 2021. 

Después del 31 de julio de 2021, los usuarios pueden seguir usando Skype Empresarial sin interrupciones en sus reuniones en línea; sin embargo, las organizaciones tendrán que habilitar a sus usuarios para las Audioconferencias proporcionadas por Microsoft si requieren audioconferencia de acceso telefónico local con Skype Empresarial o Microsoft Teams. Para obtener más información sobre Audioconferencia de Microsoft, vea [Audioconferencia.](https://products.office.com/skype-for-business/audio-conferencing) 

Según el estado final deseado de una organización, se pueden seguir tres rutas:

- Migrar a Microsoft Audioconferencia. 
- Continúe usando por separado un proveedor de servicios de audioconferencia de terceros. 
- Dejar de usar las conferencias de acceso telefónico local por completo.

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>Ruta #1: Migrar a Microsoft Audioconferencia   

Las organizaciones que decidan migrar a Microsoft Audioconferencia y completen su migración antes del 31 de julio de 2021, no experimentarán ningún impacto en el servicio durante o después de esa fecha. La migración a Microsoft Audioconferencia introducirá los siguientes cambios en una organización: 

- El servicio se facturará con todos los demás servicios de Microsoft 365 u Office 365. 

- Si se compra la suscripción estándar, el costo de acceso telefónico gratuito se incluirá en el costo de la suscripción mensual por usuario. 

- Cada organización y sus usuarios recibirán un nuevo conjunto de números de teléfono de acceso telefónico local. Para ver la cobertura geográfica del servicio de Audioconferencia de Microsoft, consulte la disponibilidad del país y la región para los planes de [audioconferencia y llamadas.](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
 
- Las reuniones que ya han programado los usuarios habilitadas con un ACP de terceros se volverán a programar automáticamente para incluir la información de acceso telefónico local de Audioconferencia de Microsoft.
 
- Los identificadores de conferencia de cada reunión serán dinámicos, lo que significa que cada reunión tendrá su propio identificador de conferencia dedicado. Los dinámicos ID de conferencia proporcionan una seguridad mejorada y una experiencia mejorada para las reuniones todo el día.

- Todo el uso del servicio está sujeto a los términos de uso de los servicios de Audioconferencia. 

Migrar a Microsoft Audioconferencia es sencillo, y se puede hacer en un par de pasos después de adquirir las licencias para el servicio. Para obtener información sobre cómo migrar a Microsoft Audioconferencia, vea:

- [Probar o comprar Audioconferencia en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**Resumen:**

- Las organizaciones que migran a Microsoft Audioconferencia y completan su migración antes del 31 de julio de 2021, no verán ningún impacto en su servicio durante o después de esa fecha.

- Para obtener más información sobre cómo migrar a Audioconferencia de Microsoft, vea Probar o comprar Audioconferencia en [Microsoft 365 u Office 365.](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>Ruta #2: Continuar usando por separado un proveedor de servicios de audioconferencia de terceros

Las organizaciones que decidan seguir usando un ACP de terceros en y después del 31 de julio de 2021 experimentarán un impacto en el servicio, ya que la información de acceso telefónico ACP de terceros ya no podrá usarse para unirse a la parte de audio de una reunión de Skype Empresarial. 

Para evitar la fragmentación del audio en las reuniones de Skype Empresarial haciendo que algunos participantes se unan a través de VoIP y otros a través del ACP de terceros, se recomienda a estas organizaciones deshabilitar el uso de VoIP en las reuniones de sus usuarios. De esta forma, todos los participantes tendrán que unirse a la parte de audio de una reunión usando el ACP de terceros y todas las demás cargas de trabajo de la reunión (como el chat o el uso compartido de la pantalla) pueden seguir siendo compatibles con Skype Empresarial. 

- Para deshabilitar VoIP de todas las reuniones de un organizador determinado, establezca el parámetro AllowIPAudio de su directiva de conferencia en false a través del cmdlet Set-CsConferencingPolicy web. Para obtener más información, [consulte Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
En lo que respecta a la programación, y a partir del 31 de julio de 2021, la información de acceso telefónico de un ACP de terceros ya no se incluirá automáticamente en las invitaciones a reuniones de Skype Empresarial. Los usuarios tendrán que agregar manualmente la información de acceso telefónico en las invitaciones a reuniones de Skype Empresarial si desean seguir incluyendo esta información como parte de sus reuniones. 

Tenga en cuenta que el 31 de julio de 2021, las reuniones existentes de los usuarios no se volverán a programar automáticamente para quitar cualquier información de acceso telefónico ACP de terceros. Las organizaciones que deciden mantener habilitada la característica VoIP para las reuniones de sus usuarios deben considerar deshabilitar la integración del ACP de terceros para sus usuarios y volver a programar sus reuniones usando el servicio de migración de reuniones para quitar la información de acceso telefónico de las conferencias de audio de terceros de sus reuniones existentes y evitar la fragmentación del audio en reuniones ya programadas. 

- Para deshabilitar la integración de audioconferencias de terceros para un organizador determinado, use el Remove-CsUserAcp cmdlet. Para obtener información adicional, [vea Remove-CsUserAcp.](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Para volver a programar automáticamente las reuniones de los usuarios después de deshabilitar la integración con un proveedor de servicios de audioconferencia de terceros, vea "¿Cómo ejecutar la migración de reuniones manualmente para un usuario?" en [Configurar el servicio de migración de reuniones (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md) 

**Resumen:**

- Las organizaciones que decidan seguir usando un ACP de terceros y después del 31 de julio de 2021 se verán afectadas porque un ACP de terceros no podrá usarse para unirse a una reunión de Skype Empresarial y las nuevas reuniones no incluirán información de acceso telefónico acp de terceros. 

- Se recomienda deshabilitar VoIP para todas las reuniones de todos los usuarios afectados antes del 31 de julio de 2021 para evitar que el audio se fragmenta entre los participantes que se unan a través de VoIP y a través de un ACP de terceros. 

    - Para deshabilitar VoIP de todas las reuniones de un organizador determinado, establezca el parámetro AllowIPAudio de la directiva de conferencia del usuario en false a través del cmdlet Set-CsConferencingPolicy. Para obtener más información, [consulte Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
- Si una organización no deshabilita VoIP para todas las reuniones, se recomienda que se deshabilite a los usuarios para que no usen la integración de Skype Empresarial Online con un ACP de terceros y que reprogramen sus reuniones para quitar la información de acceso telefónico acp de terceros para evitar la fragmentación del audio.

    - Para deshabilitar la integración de audioconferencias de terceros para un organizador determinado, use el cmdlet [Remove-CsUserAcp.](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) 

    - Para volver a programar automáticamente las reuniones, vea "¿Cómo ejecutar la migración de reuniones manualmente para un usuario?" en [Configurar el servicio de migración de reuniones (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>Ruta #3: Dejar de usar las conferencias de acceso telefónico local por completo

Las organizaciones que deciden dejar de usar las conferencias de acceso telefónico local por completo (ni proporcionados por Microsoft ni por un ACP de terceros) pueden depender completamente de VoIP para admitir la parte de audio de una reunión de Skype Empresarial. 

Estas organizaciones deban deshabilitar a sus usuarios para que no usen un proveedor de servicios de audioconferencia de terceros y que sus reuniones se reprogramen automáticamente usando el servicio de migración de reuniones para quitar su información de conferencias de acceso telefónico local. 

- Para deshabilitar la integración de audioconferencias de terceros para un organizador determinado, use el Remove-CsUserAcp cmdlet. Para obtener información adicional, [vea Remove-CsUserAcp.](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Para volver a programar automáticamente las reuniones de los usuarios después de deshabilitar la integración con un proveedor de servicios de audioconferencia de terceros, vea "¿Cómo ejecutar la migración de reuniones manualmente para un usuario?" en [Configurar el servicio de migración de reuniones (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md) 

**Resumen:** 

- Las organizaciones que decidan dejar de usar las audioconferencias antes del 31 de julio de 2021 no se verán afectadas.

- Para deshabilitar la integración de audioconferencias de terceros para un organizador determinado, use el Remove-CsUserAcp cmdlet. Para obtener información adicional, [vea Remove-CsUserAcp.](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Para volver a programar automáticamente las reuniones de los usuarios después de deshabilitar la integración con proveedores de audioconferencias de terceros, vea "¿Cómo ejecutar la migración de reuniones manualmente para un usuario?" en [Configurar el servicio de migración de reuniones (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)
