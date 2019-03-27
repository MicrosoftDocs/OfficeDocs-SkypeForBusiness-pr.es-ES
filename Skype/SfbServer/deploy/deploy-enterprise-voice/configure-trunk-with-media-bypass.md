---
title: Configurar un tronco con desvío de medios en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 'Resumen: Configurar un tronco con desvío de medios habilitado para Skype para Business Server. Esto le permitirá minimizar el número de servidores de mediación, suponiendo que el proveedor de troncos SIP lo admite.'
ms.openlocfilehash: e63ec28f863f93eed03eb4a1d2955c90434cc6ce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892691"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurar un tronco con desvío de medios en Skype para Business Server

**Resumen:** Configurar un tronco con desvío de medios habilitado para Skype para Business Server. Esto le permitirá minimizar el número de servidores de mediación, suponiendo que el proveedor de troncos SIP lo admite.

Siga estos pasos para configurar un tronco con la omisión de medios habilitada. Para configurar un tronco con desvío de medios deshabilitado, vea [Configure un tronco sin medios desvío en Skype para Business Server](configure-trunk-without-media-bypass.md).

Desvío de medios es útil cuando desea minimizar el número de servidores de mediación implementados. Para obtener más información, vea [Plan para los medios de desvío en Skype para la empresa](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Se recomienda habilitar la omisión de medios. Ahora bien, antes de hacerlo en un tronco SIP, asegúrese de que su proveedor de troncos SIP cualificado es compatible con la omisión de medios y puede aceptar los requisitos para habilitar correctamente el escenario. En concreto, el proveedor debe tener las direcciones IP de servidores en la red interna de la organización.

> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de enlace de red telefónica conmutada (RTC), los sistemas IP-PBX y los controladores de borde de sesión (SBC). Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados. Desvío de medios es compatible solo con productos y versiones que se enumeran en la página de la [Infraestructura de telefonía de Skype para Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) .

Una configuración de tronco tal como se describe más abajo agrupa un conjunto de parámetros que se aplican a los troncos a los que se ha asignado esta configuración de tronco. Una configuración de tronco concreta puede tener ámbito global (todos los troncos que no tengan una configuración de sitio o grupo de servidores más concreta), de sitio o de grupo de servidores. La configuración de tronco de nivel de grupo de servidores se utiliza para limitar el ámbito de una configuración de tronco concreta a un único tronco.

### <a name="to-configure-a-trunk-with-media-bypass"></a>Para configurar un tronco con omisión de medios

1. Abra Skype para el Panel de Control de servidor empresarial

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración de tronco**.

3. En la página **Configuración de tronco**, use uno de los métodos siguientes para configurar un tronco:

   - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración de tronco**.

   - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:

   - **Tronco del sitio**: elija el sitio para esta configuración de tronco en **Seleccionar un sitio** y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, este no aparecerá en **Seleccionar un sitio**. Esa configuración de tronco se aplicará a todos los troncos del sitio.

   - **Tronco del grupo**: elija el nombre del tronco al que se aplica esta configuración de tronco. Este tronco puede ser el tronco raíz o cualquier troncos adicionales definidas en el generador de topología. En **Seleccionar un servicio**, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración para un tronco específico, dicho tronco no aparecerá en **Seleccionar un servicio**.

      > [!NOTE]
      > Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar. > el campo **nombre** se rellena automáticamente con el nombre de sitio de la configuración del tronco o servicio asociado y no se puede cambiar.

4. Especifique un valor en **Número máximo de diálogos iniciales admitidos**. Es el número máximo de respuestas bifurcadas que una puerta de enlace de red telefónica conmutada (RTC), un sistema PBX IP o el controlador de borde de sesión (SBC) del proveedor de servicios puede recibir para una invitación (INVITE) enviada al servidor de mediación. El valor predeterminado es 20.

    > [!NOTE]
    > Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema.

5. Seleccione una de las opciones de  **Nivel admitido de cifrado** siguientes:

   - **Obligatorio**: es preciso usar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).

   - **Opcional**: se usará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.

   - **No admitido**: el proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá usar.

6. Active la casilla **Habilitar omisión de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.

    > [!IMPORTANT]
    > Para que la omisión de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades. Para obtener información detallada, vea [Plan para los medios de desvío en Skype para la empresa](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

7. Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.

8. Si el par de tronco admite la recepción de solicitudes SIP REFER desde el servidor de mediación, active la casilla de verificación **Habilitar el envío de hacer referencia a la puerta de enlace** .

    > [!NOTE]
    > Si deshabilita esta opción mientras la opción **Habilitar omisión de medios** está seleccionada, se requerirá una configuración adicional. Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet **Set-CsTrunkConfiguration** para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para la omisión de medios. También puede seleccionar **Habilitar referencia mediante el control de llamadas a terceros** si desea que los medios omitan las llamadas transferidas y la puerta de enlace no admita solicitudes SIP REFER.

9. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de la RTC a esta configuración de tronco. Para todas las llamadas entrantes a través del tronco que no se origina desde un Skype para extremo Business Server se aplicarán los usos de RTC asociados a esta configuración de tronco. Para administrar registros de uso de la RTC asociados a una configuración de tronco, use uno de los métodos siguientes:

   - Para seleccionar uno o varios registros de una lista de todos los registros de uso de RTC disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

     - Para seleccionar una o varias rutas de la lista de todas las rutas disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.

     - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).

     - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

     - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:

       a. Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.

       b. Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para seleccionar una o varias rutas de la lista de todas las rutas disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. Para obtener información detallada, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md).

   - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

     > [!IMPORTANT]
     > Es importante asociar los registros de uso de RTC según el mismo nivel de servidor de mediación que está asociado el tronco que se está configurando. Si el par de servidor de mediación es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no está asociada a un registro de uso de RTC que enruta a un destino de RTC o cualquier otros sistemas indirectos conectado a través de Skype para Business Server.

10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, seleccione el registro de uso de RTC y haga clic en arriba o flecha abajo.

    > [!IMPORTANT]
    > El orden en el que aparecen en la lista de configuración del tronco los registros de uso de RTC es importante. Skype para Business Server recorre la lista de arriba a abajo.

11. Debe seleccionarse **Habilitar cierre RTP** si se desea habilitar la omisión de medios para clientes situados detrás de una traducción de direcciones de red (NAT) o firewall y un SBC que admita cierre.

12. Debe seleccionarse **Habilitar el historial de llamadas** para habilitar el envío de información del historial de llamadas para el mismo nivel de puerta de enlace del servidor de mediación.

13. **Habilitar reenvío de datos P-Asserted-Identity** debe seleccionarse para habilitar la información de autor de llamada de P-Asserted-Identity (PAI) se transfieran entre el servidor de mediación y la puerta de enlace (y viceversa), cuando la presentación.

14. Debe seleccionar la opción **Habilitar temporizador de conmutación por error del enrutamiento de salida** para que la conmutación por error sea más rápida. La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente. Reenrutamiento a otra tronco, se producirá si no se recibe esta notificación por el servidor de mediación. En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.

15. (Opcional) Asocie y configure **Reglas de traducción de números de llamada** para el tronco. Estas reglas de conversión se aplican al número desde donde se realizó la llamada (para las llamadas salientes).

    - Para elegir una o varias reglas de una lista de todas las reglas de conversión que están disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.

    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener información detallada acerca de las reglas de conversión, vea [reglas de conversión de Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.

    - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**.

    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

    > [!CAUTION]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.

16. (Opcional) Asocie y configure **Reglas de traducción de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.

    - Para elegir una o varias reglas de una lista de todas las reglas de conversión que están disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.

    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener información detallada acerca de las reglas de conversión, vea [reglas de conversión de Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.

    - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**.

    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

    > [!CAUTION]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.

17. Asegúrese de que las reglas de conversión del tronco se organizan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en arriba o flecha abajo.

    > [!IMPORTANT]
    > Skype para Business Server recorre la lista de reglas de traducción desde la parte superior hacia abajo y utiliza la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida con sólo los números de 11 dígitos que empiecen por + 1425, debe asegurarse de que la regla que coincide con cualquier número de 11 dígitos está ordenado *que aparece a continuación* la más restrictiva regla.

18. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.

19. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Al crear o modificar la configuración de un tronco, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.

Una vez haya configurado el tronco, continúe configurando medios desvío eligiendo entre medios global Omitir opciones, tal como se describe en [el desvío de medios Deploy en Skype para Business Server](deploy-media-bypass.md) en la documentación de implementación.
## <a name="see-also"></a>Consulte también

[Configurar un tronco sin desvío de medios en Skype para Business Server](configure-trunk-without-media-bypass.md)

[Implementar el desvío de medios en Skype para Business Server](deploy-media-bypass.md)

[Definición de reglas de conversión](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[Configurar el desvío de medios](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

