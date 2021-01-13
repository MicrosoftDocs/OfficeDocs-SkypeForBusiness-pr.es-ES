---
title: Configurar un tronco con desvío de medios en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 'Resumen: configure un tronco con la omisión de medios habilitada para Skype Empresarial Server. Esto le permitirá minimizar el número de servidores de mediación, presumiendo que el proveedor de troncos SIP lo admite.'
ms.openlocfilehash: 66cb30a3de3680f562596bbbaa5b04ce1d1fbe98
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804070"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurar un tronco con desvío de medios en Skype Empresarial Server

**Resumen:** Configure un tronco con la omisión de medios habilitada para Skype Empresarial Server. Esto le permitirá minimizar el número de servidores de mediación, presumiendo que el proveedor de troncos SIP lo admite.

Siga estos pasos para configurar un tronco con la omisión de medios habilitada. Para configurar un tronco con la omisión de medios deshabilitada, consulte Configurar un tronco sin desvío [de medios en Skype Empresarial Server.](configure-trunk-without-media-bypass.md)

El desvío de medios es útil para minimizar la cantidad de servidores de mediación implementados. Para obtener más información, vea [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Te recomendamos encarecidamente que habilites la omisión de medios. Sin embargo, antes de habilitar la omisión de medios en un tronco SIP, confirme que su proveedor de troncos SIP cualificado admite la omisión de medios y puede adaptarse a los requisitos para habilitar correctamente el escenario. En concreto, el proveedor debe tener las direcciones IP de los servidores en la red interna de la organización.

> [!NOTE]
> La omisión de medios no interoperará con todas las puertas de enlace de red telefónica conmutada (RTC), IP-PBX y controlador de borde de sesión (SBC). Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados. La omisión de medios solo se admite con productos y versiones que aparecen en la página Infraestructura de telefonía [para Skype Empresarial Server.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)

Una configuración de tronco tal como se describe a continuación agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se utiliza para adaptar una configuración de tronco específica a un único tronco.

### <a name="to-configure-a-trunk-with-media-bypass"></a>Para configurar un tronco con desvío de medios

1. Abrir el Panel de control de Skype Empresarial Server

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.

3. En la página **Configuración del tronco**, utilice uno de los métodos siguientes para configurar un tronco:

   - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.

   - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:

   - **Tronco del sitio:** elija el sitio para esta configuración de tronco en Seleccionar un sitio y, **a** continuación, haga clic en **Aceptar.** Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.

   - **Tronco de grupo:** elija el nombre del tronco al que se aplica esta configuración de tronco. Este tronco puede ser el tronco raíz o cualquier tronco adicional definido en topology Builder. En **Seleccionar un servicio,** haga clic **en Aceptar.** Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.

      > [!NOTE]
      > Una vez seleccionado el ámbito de la configuración de tronco, no se podrá cambiar. > el **campo** Nombre se ha precargado con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.

4. Especifique un valor en **el número máximo de cuadros de diálogo iniciales admitidos.** Este es el número máximo de respuestas bifurcadas que una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o controlador de borde de sesión (SBC) de ITSP puede recibir a una INVITACIÓN que envió al servidor de mediación. El valor predeterminado es 20.

    > [!NOTE]
    > Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema.

5. Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:

   - **Obligatorio**: es preciso utilizar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).

   - **Opcional**: Se utilizará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.

   - **No admitido**: El proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá utilizar.

6. Active la casilla **Habilitar desvío de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.

    > [!IMPORTANT]
    > Para que el desvío de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades. Para obtener más información, consulte [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

7. Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.

8. Si el tronco del mismo nivel admite la recepción de solicitudes SIP REFER desde el servidor de mediación, active la casilla Habilitar envío para consultar la puerta **de** enlace.

    > [!NOTE]
    > Si deshabilita esta opción mientras la opción **Habilitar desvío de medios** está seleccionada, se requerirá una configuración adicional. Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet **Set-CsTrunkConfiguration** para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para el desvío de medios. Como alternativa, puede seleccionar Habilitar referencia mediante **el control** de llamadas de terceros si desea que se omita el medio de llamadas transferidas y la puerta de enlace no admite solicitudes SIP REFER.

9. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure los registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes a través del tronco que no se origine en un extremo de Skype Empresarial Server. Para administrar los registros de uso de RTC asociados a una configuración de tronco, use uno de los métodos siguientes:

   - Para seleccionar uno o más registros de una lista de todos los registros de uso de RTC disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.

   - Para quitar un registro de uso de RTC de esta configuración de tronco, resalte el registro y haga clic en **Quitar**.

   - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco:

     a. Haga clic en **Nuevo**.

     b. En el campo **Nombre**, especifique un nombre descriptivo único para el registro.

     > [!NOTE]
     > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**.

     c. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

     - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.

     - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

     - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.

     d. Haga clic en **Aceptar**.

     - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco, lleve a cabo lo siguiente:

       a. Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.

       b. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:

   - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.

   - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.

   - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. Para obtener más información, [consulte Crear o modificar una ruta de voz en Skype Empresarial.](create-or-modify-a-voice-route.md)

   - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.

     c. Haga clic en **Aceptar**.

     > [!IMPORTANT]
     > Es importante asociar los registros de uso de RTC de acuerdo con el sistema del mismo nivel del servidor de mediación asociado al tronco que se está configurando. Si el servidor de mediación del mismo nivel es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no esté asociada a un registro de uso de RTC que enruta a un destino RTC o a cualquier otro sistema de bajada conectado a través de Skype Empresarial Server.

10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, seleccione el registro de uso de RTC y haga clic en las flechas arriba o abajo.

    > [!IMPORTANT]
    > Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC. Skype Empresarial Server recorre la lista de arriba abajo.

11. Se debe seleccionar habilitar el cierre **RTP** para habilitar el desvío de medios para los clientes detrás de una traducción de direcciones de red (NAT) o firewall y un SBC que admita el cierre.

12. **Se debe seleccionar habilitar el historial** de llamadas de reenvío para habilitar el envío de información del historial de llamadas al punto de puerta de enlace del servidor de mediación.

13. Se debe seleccionar habilitar el reenvío de datos **P-Asserted-Identity** para permitir que la información del autor de la llamada P-Asserted-Identity (PAI) se reenvía entre el lado del servidor de mediación y el lado de la puerta de enlace (y viceversa), cuando esté presente.

14. **Habilitar temporizador de conmutación por error de enrutamiento saliente** debe seleccionarse para habilitar la conmutación por error rápida. La puerta de enlace asociada a este tronco puede proporcionar información cada 10 segundos durante el procesamiento de una llamada saliente. Si el servidor de mediación no recibe esta notificación, se volverá a enrir a otro tronco. Es necesario deshabilitar la conmutación por error rápida en las redes en las que la latencia puede retrasar el tiempo de respuesta o si la puerta de enlace tarda más de 10 segundos en responder.

15. (Opcional) Asocie y configure las **Reglas de traducción de números de llamada** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.

    - Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.

    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre las reglas de conversión, [consulte Reglas de traducción en Skype Empresarial Server.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)

    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.

    - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**.

    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

    > [!CAUTION]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.

16. (Opcional) Asocie y configure las **Reglas de traducción de números llamados** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.

    - Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.

    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre las reglas de conversión, [consulte Reglas de traducción en Skype Empresarial Server.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)

    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.

    - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**.

    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

    > [!CAUTION]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.

17. Asegúrese de que las reglas de conversión del tronco estén organizadas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.

    > [!IMPORTANT]
    > Skype Empresarial Server recorre la lista de reglas de conversión de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solo con números de  11 dígitos que comiencen por +1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se ordene debajo de la regla más restrictiva.

18. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.

19. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

    > [!NOTE]
    > Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [consulte Publicar los cambios pendientes en la configuración](voice-route-config-changes.md) de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.

Después de configurar el tronco, siga configurando la omisión de medios eligiendo entre las opciones globales de omisión de medios, como se describe en Implementar la omisión de medios en [Skype Empresarial Server](deploy-media-bypass.md) en la documentación sobre implementación.
## <a name="see-also"></a>Ver también

[Configurar un tronco sin desvío de medios en Skype Empresarial Server](configure-trunk-without-media-bypass.md)

[Implementar la omisión de medios en Skype Empresarial Server](deploy-media-bypass.md)

[Definición de reglas de conversión](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[Configurar el desvío de medios](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

