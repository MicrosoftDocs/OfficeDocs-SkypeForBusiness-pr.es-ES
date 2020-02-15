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
ms.openlocfilehash: 293c39884c1ef6c8e82521b3fd248ae6bbc18d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009553"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurar un tronco con la omisión de medios en Skype empresarial Server

Siga estos pasos para configurar un tronco con la omisión de medios habilitada. Para configurar un tronco con la omisión de medios deshabilitada, vea [Configure a Trunks without media bypass in Skype for Business Server](configure-a-trunk-without-media-bypass.md). El desvío de medios es útil para minimizar la cantidad de servidores de mediación implementados. En general, un grupo de servidores de mediación se implementa en un sitio central y controla puertas de enlace en los sitios de sucursal. Habilitar el desvío de medios permite que las llamadas de red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Las rutas de llamadas salientes de Skype empresarial Server y las directivas de Enterprise Voice deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.

Se recomienda habilitar la omisión de medios. Sin embargo, antes de habilitar la omisión de medios en un tronco SIP, confirme que su proveedor de tronco SIP calificado admite la omisión de medios y puede acomodar los requisitos para habilitar correctamente el escenario. Concretamente, el proveedor debe tener las direcciones IP de los servidores en la red interna de la organización. Si el proveedor no es compatible con este escenario, el desvío de medios no se efectuará correctamente. Para obtener más información, consulte [Plan for Media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace de red telefónica conmutada (RTC), IP-PBX y el controlador de borde de sesión (SBC). Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones que se enumeran en la página [infraestructura de telefonía para Skype empresarial Server](../../../SfbPartnerCertification/certification/infra-gateways.md) . 


Una configuración de tronco tal como se describe a continuación agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se utiliza para adaptar una configuración de tronco específica a un único tronco.

**Para configurar un tronco con desvío de medios**

1. Abra el panel de control de Skype empresarial Server.
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
3. En la página **Configuración del tronco**, utilice uno de los métodos siguientes para configurar un tronco:
    - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.
    - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        - **Tronco del sitio**: elija el sitio para esta configuración de tronco en **seleccionar un sitio**y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.
        - **Tronco de grupo**: elija el nombre del tronco al que se aplica esta configuración de tronco. Este tronco puede ser el tronco raíz o los troncos adicionales definidos en el generador de topologías. En **seleccionar un servicio**, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.
    
    > [!NOTE]
    > Una vez seleccionado el ámbito de la configuración de tronco, no se podrá cambiar. El campo **Nombre** está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar. 

5. Especifique un valor en **número máximo de diálogos iniciales admitidos**. Número máximo de respuestas bifurcadas que puede recibir una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un controlador de borde de sesión (SBC) ITSP a una invitación enviada al servidor de mediación. El valor predeterminado es 20.

    > [!NOTE] 
    > Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema. 

6. Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:
    - **Obligatorio**: es preciso utilizar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).
    - **Opcional**: Se utilizará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.
    - **No admitido**: El proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá utilizar.
7. Active la casilla **Habilitar desvío de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.

    > [!IMPORTANT]
    > Para que el desvío de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades. Para obtener más información, consulte [Plan for Media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.
9. Si el tronco del mismo nivel admite la recepción de solicitudes SIP REFER del servidor de mediación, active la casilla de verificación **Habilitar la referencia de envío a la puerta de enlace** . 

    > [!NOTE] 
    > Si deshabilita esta opción mientras la opción **Habilitar desvío de medios** está seleccionada, se requerirá una configuración adicional. Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet **Set-CsTrunkConfiguration** para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para el desvío de medios. Como alternativa, puede seleccionar **Habilitar referencia mediante el control de llamadas de terceros** si desea que se omitan los medios de las llamadas transferidas, y la puerta de enlace no admite solicitudes de referencia SIP. 

10. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure los registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes a través del tronco que no se originen desde un punto de conexión de Skype empresarial Server. Para administrar los registros de uso de RTC asociados a una configuración de tronco, use uno de los métodos siguientes:
    - Para seleccionar uno o más registros de una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    - Para quitar un registro de uso de RTC de esta configuración de tronco, resalte el registro y haga clic en **Quitar**.
    - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco:
        1. Haga clic en  **Nuevo **.
        2. En el campo **Nombre**, especifique un nombre descriptivo único para el registro.
            > [!NOTE] 
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**. 
        3. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        4. Haga clic en **Aceptar**.
    - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco, lleve a cabo lo siguiente:
        1. Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        2. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        3. Haga clic en **Aceptar**.

    > [!Important]
    > Es importante asociar los registros de uso de RTC de acuerdo con el servidor de mediación del mismo nivel que está asociado al tronco que se está configurando. Si el servidor de mediación del mismo nivel es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no esté asociada a un registro de uso de RTC que se enrute a un destino RTC o a cualquier otro sistema indirecto conectado a través de Skype para Business Server. 

11. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en la flecha arriba o abajo.

    > [!Important]
    > Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC. Skype empresarial Server recorre la lista de arriba a abajo. 

12. **Habilite el cierre de RTP** para habilitar los medios de omisión para los clientes que se encuentren detrás de un firewall o una traducción de direcciones de red (NAT) y un SBC que admita pestillos.
13. **Habilite el historial de llamadas reenviadas** para habilitar el envío de información de historial de llamadas a la puerta de enlace del servidor de mediación.
14. **Habilitar reenvío de datos p-Asserted-Identity** debe seleccionarse para permitir que la información del autor de la llamada p-asserted-Identity (PAI) se reenvíe entre el lado del servidor de mediación y la puerta de enlace (y viceversa), cuando esté presente.
15. **Habilitar temporizador de conmutación por error de enrutamiento saliente** debe seleccionarse para habilitar la conmutación por error rápida. La puerta de enlace asociada a este tronco puede proporcionar información cada 10 segundos durante el procesamiento de una llamada saliente. Si el servidor de mediación no recibe esta notificación, se producirá el redireccionamiento a otro tronco. Es necesario deshabilitar la conmutación por error rápida en las redes en las que la latencia puede retrasar el tiempo de respuesta o si la puerta de enlace tarda más de 10 segundos en responder.
16. (Opcional) Asocie y configure las **Reglas de traducción de números de llamada** para el tronco. Estas reglas de conversión se aplican al número de llamada para las llamadas salientes.
    - Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener información detallada sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining Translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining Translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.
    > [!Warning]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

17. (Opcional) Asocie y configure las **Reglas de traducción de números llamados** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.
    - Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener información detallada sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining Translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining Translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

    > [!Warning] 
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

18. Asegúrese de que las reglas de conversión del tronco estén organizadas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.

    >[!Important] 
    > Skype empresarial Server recorre la lista de reglas de conversión de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por -1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado *debajo* de la regla más restrictiva. 

19. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.
20. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

    > [!Note]
    > Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener información detallada, consulte [Publish Pending changes to the Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). (¿NECESITA UN VÍNCULO NUEVO?)

Una vez configurado el tronco, siga configurando la omisión de medios mediante la elección entre las opciones de omisión de medios globales, como se describe en [deploy media bypass in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).

