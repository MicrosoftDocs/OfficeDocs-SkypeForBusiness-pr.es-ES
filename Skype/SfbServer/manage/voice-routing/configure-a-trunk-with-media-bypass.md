---
title: Configurar un tronco con la omisión de medios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Siga estos pasos para configurar un tronco con la omisión de medios habilitada. '
ms.openlocfilehash: 3628c0ea38c0692b313ee37ca7b836c159a5a2dd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817040"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurar un tronco con la omisión de medios en Skype empresarial Server

Siga estos pasos para configurar un tronco con la omisión de medios habilitada. Para configurar un tronco con la omisión de medios deshabilitada, vea [configurar un tronco sin omitir medios en Skype empresarial Server](configure-a-trunk-without-media-bypass.md). La omisión de elementos multimedia es útil cuando desea minimizar el número de servidores de mediación implementados. Normalmente, un grupo de servidores de mediación se implementará en un sitio central y controlará las puertas de enlace en los sitios de sucursales. Habilitar la omisión de medios permite que las llamadas de la red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Las rutas de llamadas salientes de Skype empresarial Server y las directivas de voz empresarial deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.

Se recomienda habilitar la omisión de medios. Ahora bien, antes de hacerlo en un tronco SIP, asegúrese de que su proveedor de troncos SIP cualificado es compatible con la omisión de medios y puede aceptar los requisitos para habilitar correctamente el escenario. Concretamente, el proveedor debe disponer de las direcciones IP de los servidores en la red interna de la organización. Si el proveedor no admite este escenario, la omisión de elementos multimedia no se realizará correctamente. Para obtener más información, consulte [planear la omisión de medios en Skype empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> La omisión de medios no funcionará con todas las puertas de enlace de red de telefonía pública conmutada (RTC), IP-PBX ni el controlador de borde de sesión (SBC). Microsoft ha probado una serie de puertas de enlace RTC y SBC con asociados certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. La omisión de elementos multimedia solo se admite en los productos y versiones que se enumeran en la página [infraestructura de telefonía de Skype empresarial Server](../../../SfbPartnerCertification/certification/infra-gateways.md) . 


Una configuración de tronco tal como se describe más abajo agrupa un conjunto de parámetros que se aplican a los troncos a los que se ha asignado esta configuración de tronco. Una configuración de tronco concreta puede tener ámbito global (todos los troncos que no tengan una configuración de sitio o grupo de servidores más concreta), de sitio o de grupo de servidores. La configuración de tronco de nivel de grupo de servidores se utiliza para limitar el ámbito de una configuración de tronco concreta a un único tronco.

**Para configurar un tronco con omisión de medios**

1. Abra el panel de control de Skype para Business Server.
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración de tronco**.
3. En la página **Configuración de tronco**, use uno de los métodos siguientes para configurar un tronco:
    - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración de tronco**.
    - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        - **Tronco del sitio**: elija el sitio para esta configuración de tronco en **Seleccionar un sitio** y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, este no aparecerá en **Seleccionar un sitio**. Esa configuración de tronco se aplicará a todos los troncos del sitio.
        - **Tronco del grupo**: elija el nombre del tronco al que se aplica esta configuración de tronco. Este tronco puede ser el tronco raíz o cualquier otro tipo de troncos definidos en el generador de topologías. En **Seleccionar un servicio**, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración para un tronco específico, dicho tronco no aparecerá en **Seleccionar un servicio**.
    
    > [!NOTE]
    > Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar. El campo **Nombre** está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar. 

5. Especifique un valor en **Número máximo de diálogos iniciales admitidos**. Es el número máximo de respuestas bifurcadas que una puerta de enlace de red telefónica conmutada (RTC), un sistema PBX IP o el controlador de borde de sesión (SBC) del proveedor de servicios puede recibir para una invitación (INVITE) enviada al servidor de mediación. El valor predeterminado es 20.

    > [!NOTE] 
    > Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema. 

6. Seleccione una de las opciones de  **Nivel admitido de cifrado** siguientes:
    - **Obligatorio**: es preciso usar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).
    - **Opcional**: se usará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.
    - **No admitido**: el proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá usar.
7. Active la casilla **Habilitar omisión de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.

    > [!IMPORTANT]
    > Para que la omisión de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades. Para obtener más información, consulte [planear la omisión de medios en Skype empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.
9. Si el tronco del mismo nivel admite la recepción de solicitudes SIP de referencia del servidor de mediación, seleccione la casilla de verificación **Habilitar envío consulte la puerta de enlace** . 

    > [!NOTE] 
    > Si deshabilita esta opción mientras la opción **Habilitar omisión de medios** está seleccionada, se requerirá una configuración adicional. Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet **Set-CsTrunkConfiguration** para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para la omisión de medios. También puede seleccionar **Habilitar referencia mediante el control de llamadas a terceros** si desea que los medios omitan las llamadas transferidas y la puerta de enlace no admita solicitudes SIP REFER. 

10. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de la RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán para todas las llamadas entrantes a través del tronco que no se originen desde un punto de conexión de Skype empresarial Server. Para administrar registros de uso de la RTC asociados a una configuración de tronco, use uno de los métodos siguientes:
    - Para seleccionar uno o varios registros de una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    - Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar**.
    - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:
        1. Haga clic en **Nuevo**.
        2. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
            > [!NOTE] 
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**. 
        3. Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        4. Haga clic en **Aceptar**.
    - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:
        1. Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        2. Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        3. Haga clic en **Aceptar**.

    > [!Important]
    > Es importante asociar los registros de uso de RTC según el servidor de mediación del mismo nivel que esté asociado al tronco que se configure. Si el servidor de mediación del mismo nivel es una puerta de enlace o un controlador de borde de sesión (SBC), se recomienda enfáticamente que la configuración de troncal no esté asociada a un registro de uso de RTC que se dirija a un destino RTC o a cualquier otro sistema indirecto conectado a través de Skype. para Business Server. 

11. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en las flechas arriba o abajo.

    > [!Important]
    > El orden en el que aparecen en la lista de configuración del tronco los registros de uso de RTC es importante. Skype empresarial Server recorre la lista de arriba a abajo. 

12. Debe seleccionarse **Habilitar cierre RTP** si se desea habilitar la omisión de medios para clientes situados detrás de una traducción de direcciones de red (NAT) o firewall y un SBC que admita cierre.
13. **Habilitar el historial de llamadas hacia adelante** debe seleccionarse para habilitar el envío de información del historial de llamadas a la puerta de enlace del servidor de mediación.
14. **Habilitar Forward-Asserted: los datos de identidad** deben seleccionarse para habilitar la identidad de firma de p-asserted-Identity (PAI) la información del originador de llamadas se desviará entre el lado del servidor de mediación y la puerta de enlace (y viceversa) cuando estén presentes.
15. Debe seleccionar la opción **Habilitar temporizador de conmutación por error del enrutamiento de salida** para que la conmutación por error sea más rápida. La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente. El redireccionamiento a otro tronco se producirá si el servidor de mediación no recibe esta notificación. En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.
16. (Opcional) Asocie y configure **Reglas de traducción de números de llamada** para el tronco. Estas reglas de traducción se aplican al número de llamada para llamadas salientes.
    - Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una nueva regla, consulte [definir reglas de traducción en Skype empresarial Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte [definición de reglas de traducción en Skype empresarial Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [definición de reglas de traducción en Skype empresarial Server](defining-translation-rules.md).
    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    > [!Warning]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto. 

17. (Opcional) Asocie y configure **Reglas de traducción de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.
    - Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener más información sobre cómo definir una nueva regla, consulte [definir reglas de traducción en Skype empresarial Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte [definición de reglas de traducción en Skype empresarial Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [definición de reglas de traducción en Skype empresarial Server](defining-translation-rules.md).
    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

    > [!Warning] 
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto. 

18. Asegúrese de que las reglas de conversión del tronco se dispongan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.

    >[!Important] 
    > Skype empresarial Server recorre la lista de reglas de traducción de la parte superior abajo y usa la primera regla que coincida con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por +1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado *por debajo* de la regla más restrictiva. 

19. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.
20. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

    > [!Note]
    > Al crear o modificar la configuración de un tronco, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración del enrutamiento de voz](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). (¿NECESITA UN VÍNCULO NUEVO?)

Una vez que haya configurado el tronco, continúe con la configuración de la omisión de medios al elegir entre las opciones de omisión de multimedia global, como se describe en [implementar la omisión de medios en Skype empresarial Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).

