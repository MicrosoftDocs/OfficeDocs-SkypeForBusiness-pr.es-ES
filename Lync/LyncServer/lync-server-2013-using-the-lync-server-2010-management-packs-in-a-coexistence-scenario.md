---
title: "Usar paquetes de administración de Lync Server 2010 en un escenario de coexistencia"
TOCTitle: "Ut. des packs d’admin. de Lync Server 2010 dans un scénario de coexistence"
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48275946
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de los paquetes de administración de Lync Server 2010 en un escenario de coexistencia

 

_**Última modificación del tema:** 2012-10-22_

Muchos clientes adoptan un programa de implementación dentro de su empresa en el que los usuarios se migran de manera progresiva desde Microsoft Lync Server 2010 hasta Lync Server 2013. Los administradores de esas compañías se ocupan de supervisar las dos versiones de Lync Server para que la comunicación de sus usuarios finales sea lo mejor posible. Para ese escenario, el módulo de administración de Lync Server 2013 ofrece una ruta de migración en paralelo con el módulo de administración de Lync Server 2010.

En Lync Server 2010, se detectaron equipos de Lync Server en el documento de topología guardado con el Almacén de administración central. En esta configuración, un solo equipo informaría de la existencia de todos los demás equipos de Lync Server.

Ahora, los módulos de administración de Lync Server 2013 utilizan detección en el nivel de máquina, en lugar del mecanismo de detección central que se empleaba en Lync Server 2010. Por ello, cada agente de System Center, básicamente, se detecta a sí mismo e informa de su existencia a System Center Operations Manager. El uso de la detección en el nivel de máquina simplifica la administración de su infraestructura de System Center y, además, permite que convivan con más facilidad diferentes versiones de los módulos de administración de Lync Server (por ejemplo, los módulos de administración de Lync Server 2010 y los de Lync Server 2013).

Para esta migración, primero tiene que actualizar la supervisión de Lync Server 2010 existente, de modo que no haya lagunas en la cobertura. Para ello, elija un equipo de Lync Server 2010 existente, que revisará el script de detección central de Lync Server 2010 antes de actualizar el Almacén de administración central a Lync Server 2013. Este proceso tiene cuatro pasos:

1.  Actualice los módulos de administración de Lync Server 2010 a la actualización acumulativa 7.

2.  Ordene a un equipo de Lync Server 2010 que ejecute el script de detección central.

3.  Invalide el candidato de detección central del módulo de administración de Microsoft Lync Server 2010.

4.  Compruebe que se ha detectado el nuevo candidato de detección central.

## Ordenar a un equipo de Lync Server 2010 que ejecute el script de detección central

Para designar un equipo ajeno al Almacén de administración central (por ejemplo, un servidor front-end de Lync Server) para que se ocupe de la detección central, deberá crear la siguiente clave del Registro en el servidor ajeno al Almacén de administración central:

HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate

Puede crear esta clave del Registro llevando a cabo el siguiente procedimiento:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda **HKEY\_LOCAL\_MACHINE**, expanda **SOFTWARE**, expanda **Microsoft** y, a continuación, expanda **Real-Time Communications**.

4.  Haga clic con el botón secundario en **Health**, haga clic en **Nuevo** y, después, haga clic en **Clave**. Si no existe la clave **Health**, haga clic con el botón secundario en **Real-Time Communications**, elija **Nuevo** y, luego, haga clic en **Clave**. Cuando se haya creado la nueva clave, escriba Health y presione ENTRAR.
    
    Después de que se haya creado la nueva clave, escriba **CentralDiscoveryCandidate** y presione ENTRAR para cambiar el nombre de la clave.

El equipo puede tardar varias horas en adoptar este cambio. Para que el cambio se aplique de inmediato, detenga el servicio Agente de mantenimiento y reinícielo. Para reiniciar el servicio Agente de mantenimiento, lleve a cabo el siguiente procedimiento en el equipo de Lync Server 2010:

1.  Haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.

2.  En la ventana de la consola, escriba el siguiente comando y presione ENTRAR:
    
        Net stop HealthService

3.  Verá el siguiente mensaje: "El servicio de administración de System Center se está deteniendo", seguido de un segundo mensaje para informarle de que el servicio se ha detenido. Después de que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando ENTRAR:
    
        Net start HealthService

## Invalidación del candidato de detección central del módulo de administración de Lync Server 2010

Después de ordenar a un equipo de Lync Server 2010 que informe de los equipos de Lync Server 2010, deberá informar también al módulo de administración de Lync Server 2010 acerca de este cambio. Para ello, tendrá que crear una invalidación en el módulo de administración. Se puede hacer siguiendo este procedimiento:

1.  En la consola de Operations Manager, haga clic en **Creación**.

2.  En la pestaña Creación, expanda **Objetos del módulo de administración**, haga clic en **Detecciones de objetos** y, después, haga clic en **Ámbito**.

3.  En el cuadro de diálogo **Objetos de módulo de administración de ámbito**, seleccione el elemento que tenga el **candidato de detección de LS** de destino y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que el candidato de detección de LS aparecerá solamente si ha instalado el módulo de administración de Lync Server 2010.

4.  En la consola de Operations Manager, haga clic con el botón secundario en **Candidato de detección de LS**, elija **Invalidaciones**, elija **Invalidar la detección de objetos** y, luego, haga clic en **Para todos los objetos de la clase: candidato de detección de LS**.

5.  En el cuadro de diálogo **Propiedades de invalidación**, active la casilla **Invalidar** que hay junto al parámetro **Fqdn de WatcherNode de detección central**. Escriba el nombre de dominio completo del equipo de Lync Server 2010 en los cuadros **Invalidar valor** y **Valor efectivo**. Active la casilla **Aplicado** y haga clic en **Aceptar**.

Una vez haya creado la invalidación, debe reiniciar el servicio de mantenimiento del Servidor de administración raíz. Para reiniciar el servicio de mantenimiento, lleve a cabo el siguiente procedimiento en el Servidor de administración raíz:

1.  Haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.

2.  En la ventana de la consola, escriba el siguiente comando y presione ENTRAR:
    
        Net stop HealthService

3.  Verá el siguiente mensaje: "El servicio de administración de System Center se está deteniendo", seguido de un segundo mensaje para informarle de que el servicio se ha detenido. Después de que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando ENTRAR:
    
        Net start HealthService

## Comprobar que se detectó el nuevo candidato de detección central

El último paso antes de actualizar el Almacén de administración central es asegurarse de que el módulo de administración de Lync Server 2010 detectó el nuevo candidato de detección central. Para ello, abra la consola de Operations Manager y haga clic en Supervisión. En la pestaña Supervisión, expanda **Mantenimiento de Microsoft Lync Server 2010**, expanda **Detección de topologías** y, a continuación, haga clic en **Vista de estado de detección**. Compruebe que una fila de la pantalla tiene una **Ruta** con el nombre de dominio completo del candidato de detección central. También debe comprobar que el estado del equipo es **Correcto**.

