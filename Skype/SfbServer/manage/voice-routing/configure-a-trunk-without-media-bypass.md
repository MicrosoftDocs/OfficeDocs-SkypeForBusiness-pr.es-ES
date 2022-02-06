---
title: 'Skype Empresarial Server: configurar un tronco sin desvío de medios'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Cómo configurar un tronco con la omisión de medios habilitada. '
---

# <a name="skype-for-business-server---configure-a-trunk-without-media-bypass"></a>Skype Empresarial Server: configurar un tronco sin desvío de medios

Si desea configurar un enlace troncal con el desvío de medios deshabilitado, siga estos pasos. Si desea configurar un tronco con la omisión de medios habilitada, consulte [Configure a trunk with media bypass in Skype Empresarial Server](configure-a-trunk-with-media-bypass.md).

Tal como se describe a continuación, una configuración de tronco agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se utiliza para adaptar una configuración de tronco específica a un único tronco.

**Para configurar un enlace troncal sin desvío de medios**

1. Abra Skype panel de control de Busines Server.
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
4. En la página **Configuración del tronco**, utilice uno de los métodos siguientes para configurar un tronco:
    - Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.
    - Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:
        - **Tronco del sitio**: elija el sitio para esta configuración de tronco en **Seleccionar un sitio** y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**. Esta configuración de tronco se aplicará a todos los troncos del sitio.
        - **Tronco de grupo de servidores**: elija el nombre del tronco al que se aplica esta configuración de tronco en **Seleccionar un servicio** y haga clic en **aceptar**. Este tronco puede ser el tronco raíz o cualquier tronco adicional definido en el Generador de topologías. Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.
    > [!Note] 
    > Una vez seleccionado el ámbito de la configuración de tronco, no se podrá cambiar. El campo **Nombre** está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar. 

5. Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:
    - **Obligatorio**: es preciso utilizar un protocolo de transporte seguro en tiempo real (SRTP) para contribuir a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).
    - **Opcional**: Se utilizará el cifrado del SRTP si lo admiten el proveedor de servicios o el fabricante de los equipos.
    - **No admitido**: El proveedor de servicios o el fabricante de los equipos no admite el cifrado de SRTP y, por tanto, no se podrá utilizar.
6. Asegúrese de que esté desactivada la casilla **Habilitar desvío de medios**.
7. Active la casilla de verificación **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace de red telefónica conmutada [RTC] donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.
8. Si el sistema del mismo nivel del tronco admite la recepción de solicitudes REFER SIP desde el servidor de mediación, active la casilla Habilitar envío para hacer referencia **a la puerta de** enlace.
9. (Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure los registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes a través del tronco que no se origine desde un punto de conexión Skype Empresarial Server enlace. Para administrar los registros de uso de RTC asociados a una configuración de tronco, use uno de los métodos siguientes:
    - Para seleccionar uno o varios registros de una lista de todos los registros de uso de RTC disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.
    - Para quitar un registro de uso de RTC de esta configuración de tronco, resalte el registro y haga clic en **Quitar**.
    - Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco:
        1. Haga clic en  **Nuevo**.
        2. En el campo **Nombre**, especifique un nombre descriptivo único para el registro.
            > [!Note] 
            > El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo **Nombre**. 

        3. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        4. Haga clic en **Aceptar**.
    - Para editar un registro de uso de RTC ya asociado a esta configuración de tronco, lleve a cabo lo siguiente:
        1. Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.
        2. Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:
            - Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**. 
            - Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.
            - Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**. 
            - Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**. 
        3. Haga clic en **Aceptar**.

    > [!Important] 
    > Es importante asociar los registros de uso de RTC según el servidor de mediación del mismo nivel que está asociado al tronco que se está configurando. Si el servidor de mediación es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no esté asociada a un registro de uso de RTC que enruta a un destino RTC o a cualquier otro sistema descendente conectado a través de Skype Empresarial Server. 

10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en la flecha arriba o abajo.
    > [!Important] 
    > Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC. Skype Empresarial Server recorre la lista de arriba a abajo. 

11. **Habilitar cierre de RTP** debe seleccionarse para habilitar el desvío de medios para los clientes que se encuentren detrás de un firewall o NAT y para los SBC que admitan el cierre.
12. **Se debe seleccionar Habilitar el historial de** llamadas de reenvío para habilitar el envío de información del historial de llamadas al mismo nivel de puerta de enlace del servidor de mediación.
13. **Habilitar los datos de P-Asserted-Identity** de reenvío debe seleccionarse para permitir que la información del originador de llamadas PAI se reenvía entre el lado del servidor de mediación y el lado de la puerta de enlace (y viceversa), cuando esté presente.
14. **Habilitar temporizador de conmutación por error de enrutamiento saliente** debe seleccionarse para habilitar la conmutación por error rápida. La puerta de enlace asociada a este tronco puede proporcionar información cada 10 segundos durante el procesamiento de una llamada saliente. Si el servidor de mediación no recibe esta notificación, se volverá a enrir a otro tronco. Es necesario deshabilitar la conmutación por error rápida en las redes en las que la latencia puede retrasar el tiempo de respuesta o si la puerta de enlace tarda más de 10 segundos en responder.
15. (Opcional) Asocie y **configure reglas de traducción de números de llamada** para el tronco. Estas reglas de traducción se aplican al número de llamada para las llamadas salientes.
    - Para elegir una o más reglas de una lista de todas las reglas de traducción que están disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una nueva regla, consulte [Defining translation rules in Skype Empresarial Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining translation rules in Skype Empresarial Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining translation rules in Skype Empresarial Server](defining-translation-rules.md).
    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

    > [!Warning]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

16. (Opcional) Asocie y configure las **Reglas de traducción de números llamados** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.
    - Para elegir una o más reglas de una lista de todas las reglas de traducción que están disponibles en la implementación Telefonía IP empresarial, haga clic en **Seleccionar**. En Seleccionar reglas de traducción, haga clic en las reglas que desea asociar al tronco y, a continuación, haga clic en **Aceptar**.
    - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una nueva regla, consulte [Defining translation rules in Skype Empresarial Server](defining-translation-rules.md).
    - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining translation rules in Skype Empresarial Server](defining-translation-rules.md).
    - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining translation rules in Skype Empresarial Server](defining-translation-rules.md).
    - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

    > [!Caution] 
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 

17. Asegúrese de que las reglas de traducción del tronco están organizadas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.

    > [!Important] 
    > Skype Empresarial Server recorre la lista de reglas de traducción de arriba abajo y usa la primera regla que coincide con el número marcado. Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas. Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por -1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado debajo de la regla más restrictiva. 

18. Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.
19. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 

    > [!Note]
    > Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte Publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013 en la documentación sobre operaciones. 
