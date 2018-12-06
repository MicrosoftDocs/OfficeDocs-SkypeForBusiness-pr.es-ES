---
title: "Directiva calidad servicio para servidores de conferencia, aplic. y mediación"
TOCTitle: Configurar la directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48275957
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación en Lync Server 2013

 

_**Última modificación del tema:** 2014-06-23_

Configurar intervalos de puertos facilita el uso de Calidad de servicio, al hacer que todo el tráfico de un determinado tipo (por ejemplo, todo el tráfico de audio) se transmita a través del mismo conjunto de puertos. De este modo, resulta fácil para el sistema identificar y marcar un cierto paquete: si el puerto 49152 está reservado al tráfico de audio, todos los paquetes que se transmiten a través del puerto 49152 se pueden marcar con un código DSCP que indica que se trata de paquetes de audio. A su vez, esto permite a los enrutadores identificar el paquete como un paquete de audio y darle mayor prioridad que a los paquetes sin marcar (por ejemplo, los paquetes que se usan para copiar un archivo de un servidor a otro).

Sin embargo, el solo hecho de restringir un conjunto de puertos a un tipo específico de tráfico no hace que los paquetes que se transmiten a través de esos puertos se marquen con el código DSCP correspondiente. Además de definir intervalos de puertos, debe crear directivas de Calidad de servicio que especifiquen el código DSCP que se debe asociar a cada intervalo de puertos. En Microsoft Lync Server 2013, esto suele implicar la creación de dos directivas: una para audio y otra para vídeo.

Las directivas de Calidad de servicio (QoS) se crean y se administran más fácilmente utilizando la directiva de grupo. (Estas mismas directivas también se pueden crear mediante directivas de seguridad local pero, con ese método, hay que repetir el mismo procedimiento en cada uno de los equipos.) Su conjunto inicial de directivas de QoS (una para audio y otra para vídeo) solamente se debe aplicar a los equipos Lync Server que ejecuten los servicios de servidor de conferencia, servidor de aplicaciones y/o servidor de mediación. Si todos estos equipos se encuentran en la misma OU de Active Directory, puede asignar, simplemente, el nuevo objeto de directiva de grupo (GPO) a esa OU. También puede llevar a cabo otras acciones para dirigir la nueva directiva a los equipos especificados; por ejemplo, puede colocar los equipos correspondientes en un grupo de seguridad y, a continuación, usar el filtrado de seguridad de la directiva de grupo para aplicar el GPO solamente a ese grupo de seguridad.

Para crear una directiva de Calidad de servicio destinada a la administración de audio, inicie sesión en un equipo donde se haya instalado Administración de directivas de grupo. Abra Administración de directivas de grupo (haga clic en **Inicio** , elija **Herramientas administrativas** y, después, haga clic en **Administración de directivas de grupo** ) y, a continuación, siga este procedimiento:

1.  En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva. Por ejemplo, si todos sus equipos de Lync Server se encuentran en una OU denominada Lync Server, la nueva directiva se debe crear en la OU Lync Server.

2.  Haga clic con el botón secundario en el contenedor que corresponda y, después, haga clic en **Crear un GPO en este dominio y vincularlo aquí** .

3.  En el cuadro de diálogo **Nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **Nombre** (por ejemplo, **Lync Server QoS** ) y haga clic en **Aceptar** .

4.  Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic en **Editar** .

5.  En el Editor de administración de directivas de grupo, expanda **Configuración del equipo** , expanda **Directivas** , expanda **Configuración de Windows** , haga clic con el botón secundario en **QoS basada en directivas** y, a continuación, haga clic en **Crear nueva directiva** .

6.  En el cuadro de diálogo **QoS basada en directivas** , en la página que se abre, escriba un nombre para la nueva directiva (p. ej., **Lync Server QoS** ) en el cuadro **Nombre** . Seleccione **Especificar el valor de DSCP** y establezca el valor **46** . Deje desactivada la casilla **Especificar velocidad de salida del acelerador** y haga clic en **Siguiente** .

7.  En la siguiente página, asegúrese de que está activado **Todas las aplicaciones** y haga clic en **Siguiente** . Esto sirve, simplemente, para hacer que todas las aplicaciones relacionen los paquetes del intervalo de puertos especificado con el código DSCP especificado.

8.  En la tercera página, compruebe que están activados **Cualquier dirección IP de origen y Cualquier dirección IP de destino** , y haga clic en **Siguiente** . Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.

9.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red que utilizan Lync Server y sus aplicaciones cliente con más frecuencia.

10. Debajo del encabezado **Especifique el número de puerto de origen** , seleccione **Desde este intervalo o puerto de origen** . En el cuadro de texto que acompaña a esta opción, escriba el intervalo de puertos reservado a las transmisiones de audio. Por ejemplo, si reservó los puertos del 49152 al 57500 para el tráfico de audio, introduzca el intervalo de puertos con este formato: **49152:57500** . Haga clic en **Finalizar** .


> [!NOTE]
> El valor de DSCP de 46 es algo arbitrario: aunque DSCP 46 se utiliza a menudo para marcar paquetes de audio, no es necesario que use DSCP 46 para las comunicaciones de audio. Si ya ha implementado QoS y está usando otro código DSCP para el audio (por ejemplo, DSCP 40), debe configurar la directiva de Calidad de servicio para que utilice el mismo código (es decir, 40 para el audio). Si está implementando Calidad de servicio ahora, se recomienda usar DSCP 46 para el audio, simplemente, porque es el valor que se suele usar para marcar paquetes de audio.



Después de crear la directiva de QoS para el tráfico de audio, debe crear una segunda directiva para el tráfico de vídeo (y, si lo desea, una tercera para administrar el tráfico de uso compartido de aplicaciones). Para crear una directiva destinada al vídeo, siga el mismo procedimiento básico que llevó a cabo al crear la directiva de audio, sustituyendo lo siguiente:

  - Utilice un nombre de directiva diferente (y único) (por ejemplo, **Vídeo Lync Server** ).

  - Establezca el valor de DSCP **34** en lugar de 46. (Tenga en cuenta que no es necesario usar el valor de DSCP 34. El único requisito es usar un valor de DSCP distinto para el vídeo del que se usó para el audio.)

  - Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos del 57501 al 65535 para el vídeo, establezca el intervalo de puertos así: **57501:65535** .

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera directiva, sustituyendo lo siguiente:

  - Utilice un nombre de directiva diferente (y único) (por ejemplo, **Uso compartido de aplicaciones Lync Server** ).

  - Establezca el valor de DSCP **24** en lugar de 46. (De nuevo, tenga en cuenta que no es necesario usar el valor de DSCP 24. El único requisito es usar un valor de DSCP distinto para el uso compartido de aplicaciones de los que se usaron para el audio y el vídeo.)

  - Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos del 40803 al 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos así: **40803:49151** .

Las nuevas directivas que ha creado no entrarán en vigor hasta haber actualizado la directiva de grupo en sus equipos Lync Server. Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde sea necesario actualizar la directiva de grupo:

    Gpupdate.exe /force

Este comando se puede ejecutar desde dentro de Shell de administración de Lync Server o desde cualquier ventana de comandos que se ejecute con las credenciales de administrador. Para ejecutar una ventana de comandos con credenciales de administrador, haga clic en **Inicio** , haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador** .

Para comprobar que se han aplicado las nuevas directivas de QoS, haga lo siguiente:

1.  En un equipo de Lync Server, haga clic en **Inicio** y, después, en **Ejecutar** .

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda **Equipo** , expanda **HKEY\_LOCAL\_MACHINE** , expanda **SOFTWARE** , expanda **Policies** , expanda **Microsoft** , expanda **Windows** y, a continuación, haga clic en **QoS** . Debajo de **QoS** , debería ver las claves del Registro de cada una de las directivas de QoS que acaba de crear. Por ejemplo, si creó dos nuevas directivas (una, llamada Lync Server Audio QoS, y la otra, llamada Lync Server Video QoS) debería ver las entradas del Registro de Lync Server Audio QoS y Lync Server Video QoS.

Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar** .

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda **HKEY\_LOCAL\_MACHINE** , expanda **SYSTEM** , expanda **CurrentControlSet** , expanda **services** y, a continuación, expanda **Tcpip** .

4.  Haga clic con el botón secundario en **Tcpip** , elija **Nuevo** y, a continuación, haga clic en **Clave** . Después de que se cree una nueva clave del Registro, escriba **QoS** y presione ENTRAR para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS** , elija **Nuevo** y, a continuación, haga clic en **Valor de cadena** . Después de que se cree un nuevo valor del Registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre del valor.

6.  Haga clic con el botón secundario en **No usar NLA** . En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **Información del valor** y, a continuación, haga clic en **Aceptar** .

7.  Cierre el Editor del Registro y reinicie el equipo.

