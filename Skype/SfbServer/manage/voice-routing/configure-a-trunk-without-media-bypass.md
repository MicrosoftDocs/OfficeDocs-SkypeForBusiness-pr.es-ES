---
title: Configurar un tronco sin desvío de medios en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Siga estos pasos para configurar un tronco con la omisión de medios habilitada. '
ms.openlocfilehash: 623de0439e6c6297808e54eb2ae050aa95f6533d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214669"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Configurar un tronco sin desvío de medios en Skype para Business Server

Si desea configurar un tronco con la omisión de medios deshabilitada, siga estos pasos. Si desea configurar un tronco con desvío de medios habilitado, vea [Configure un tronco con medios desvío en Skype para Business Server](configure-a-trunk-with-media-bypass.md).

Tal como se describe a continuación, una configuración de tronco agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se usa para adaptar una configuración de tronco específica a un único tronco.

**Para configurar un tronco sin omisión de medios**

1. Abra Skype para el Panel de Control de servidor de negocios.
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración de tronco**.
4. En la página **Configuración de tronco**, use uno de los métodos siguientes para configurar un tronco:
    - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración de tronco**.
    - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        - **Tronco del sitio**: elija el sitio para esta configuración de tronco en **Seleccionar un sitio**y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.
        - **Tronco de grupo de servidores**: elija el nombre del tronco al que se aplica esta configuración de tronco en  **Seleccionar un servicio** y haga clic en **Aceptar**. Este tronco puede ser el tronco raíz o cualquier troncos adicionales definidas en el generador de topología. Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.
    > [!Note] 
    > Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar. El campo **Nombre** está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar. 

5. Seleccione una de las opciones de  **Nivel admitido de cifrado** siguientes:
    - **Obligatorio**: es preciso usar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).
    - **Opcional**: se usará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.
    - **No admitido**: el proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá usar.
6. Asegúrese de que esté desactivada la casilla **Habilitar omisión de medios**.
7. Active la casilla de verificación de **medios centralizado de procesamiento** si no hay un medio Well-known punto de terminación (por ejemplo, una telefónica conmutada (RTC) de red puerta de enlace donde la terminación de medios tiene la misma IP como la terminación señalización). Si el tronco no tiene un punto de terminación de medios bien conocido, desactive esta casilla.
8. Si el par de tronco admite la recepción de solicitudes SIP REFER desde el servidor de mediación, active la casilla de verificación **Habilitar el envío de hacer referencia a la puerta de enlace** .
9. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de la RTC a esta configuración de tronco. Para todas las llamadas entrantes a través del tronco que no se origina desde un Skype para extremo Business Server se aplicarán los usos de RTC asociados a esta configuración de tronco. Para administrar registros de uso de la RTC asociados a una configuración de tronco, use uno de los métodos siguientes:
    - Para seleccionar uno o varios registros de una lista de todos los registros de uso de RTC disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    - Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar**.
    - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:
        1. Haga clic en **Nuevo**.
        2. En el campo **Nombre**, escriba un nombre descriptivo único para el registro.
            > [!Note] 
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**. 

        3. Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o varias rutas de la lista de todas las rutas disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        4. Haga clic en **Aceptar**.
    - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:
        1. Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        2. Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o varias rutas de la lista de todas las rutas disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        3. Haga clic en **Aceptar**.

    > [!Important] 
    > Es importante asociar los registros de uso de RTC según el mismo nivel de servidor de mediación que está asociado el tronco que se está configurando. Si el par de servidor de mediación es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no está asociada a un registro de uso de RTC que enruta a un destino de RTC o cualquier otros sistemas indirectos conectado a través de Skype para Business Server. 

10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en las flechas arriba o abajo.
    > [!Important] 
    > El orden en el que aparecen en la lista de configuración del tronco los registros de uso de RTC es importante. Skype para Business Server recorre la lista de arriba a abajo. 

11. Debe seleccionar la opción **Habilitar cierre RTP** para habilitar la omisión de medios para los clientes que se encuentren detrás de un firewall o NAT y para los SBC que admitan el cierre.
12. Debe seleccionarse **Habilitar el historial de llamadas** para habilitar el envío de información del historial de llamadas para el mismo nivel de puerta de enlace del servidor de mediación.
13. **Habilitar reenvío de datos P-Asserted-Identity** debe seleccionarse para habilitar la información de autor de llamada PAI se transfieran entre el servidor de mediación y la puerta de enlace (y viceversa), cuando la presentación.
14. Debe seleccionar la opción **Habilitar temporizador de conmutación por error del enrutamiento de salida** para que la conmutación por error sea más rápida. La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente. Reenrutamiento a otra tronco, se producirá si no se recibe esta notificación por el servidor de mediación. En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.
15. (Opcional) Asociar y **configurar reglas de traducción números de llamada** para el tronco. Estas reglas de conversión se aplican al número de llamada para las llamadas salientes.
    - Para elegir una o varias reglas de una lista de todas las reglas de conversión que están disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener información detallada sobre cómo definir una nueva regla, vea la [definición de reglas de conversión de Skype para Business Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte [definición de las reglas de traducción de Skype para Business Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [definición de las reglas de traducción de Skype para Business Server](defining-translation-rules.md).
    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

    > [!Warning]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto. 

16. (Opcional) Asocie y configure **Reglas de traducción de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.
    - Para elegir una o varias reglas de una lista de todas las reglas de conversión que están disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En Seleccione las reglas de traducción, haga clic en las reglas que desea asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**. Para obtener información detallada sobre cómo definir una nueva regla, vea la [definición de reglas de conversión de Skype para Business Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte [definición de las reglas de traducción de Skype para Business Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [definición de las reglas de traducción de Skype para Business Server](defining-translation-rules.md).
    - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

    > [!Caution] 
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto. 

17. Asegúrese de que las reglas de conversión del tronco se dispongan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.

    > [!Important] 
    > Skype para Business Server recorre la lista de reglas de traducción desde la parte superior hacia abajo y utiliza la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por +1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado por debajo de la regla más restrictiva. 

18. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.
19. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

    > [!Note]
    > Al crear o modificar la configuración de un tronco, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte publicar los cambios en la configuración de enrutamiento de voz en Lync Server 2013 en la documentación sobre operaciones pendientes. 
