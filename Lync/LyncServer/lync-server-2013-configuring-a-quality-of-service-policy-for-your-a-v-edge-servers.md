---
title: Directiva de calidad de servicio para los servidores perimetrales de audio y vídeo
TOCTitle: Configuración de la directiva de calidad de servicio para los servidores perimetrales de audio y vídeo
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48274474
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la directiva de calidad de servicio para los servidores perimetrales de audio y vídeo

 

_**Última modificación del tema:** 2012-10-19_

Además de crear directivas de QoS para sus servidores de conferencia, aplicación y mediación, también debe crear directivas de audio y vídeo para el lado interno de sus servidores perimetrales A/V. Sin embargo, las directivas usadas en sus servidores perimetrales son diferentes de las usadas en sus servidores de conferencia, aplicación y mediación. Para los servidores de conferencia, aplicación y mediación, especificó un intervalo de puertos de origen; con los servidores perimetrales, tiene que especificar un rango de puertos de destino. Debido a eso no puede aplicar simplemente las directivas de QoS a sus servidores perimetrales: estas directivas simplemente no funcionan. En su lugar, debe crear nuevas directivas para sus servidores perimetrales únicamente.

El siguiente procedimiento describe el proceso para crear los objetos de la directiva del grupo de Active Directory que se pueden usar para administrar la calidad de servicio en servidores perimetrales. Por supuesto, es posible que sus servidores perimetrales sean servidores independientes que no tienen cuentas de Active Directory. Si ese es el caso, puede usar la directiva de grupo en lugar de la directiva de grupo de Active Directory: la única diferencia es que debe crear estas directivas locales con el editor de directivas de grupo local y crear individualmente el mismo conjunto de directivas en cada servidor perimetral. Para iniciar el editor de directivas de grupo local en un servidor perimetral, haga lo siguiente:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar** .

2.  En el cuadro de diálogo **Ejecutar**, escriba **gpedit.msc** y, a continuación, presione ENTRAR.

Si está creando directivas basadas en Active Directory, debería iniciar sesión en un equipo donde se haya instalado Administración de directivas de grupo. En ese caso, abra Administración de directivas de grupo (haga clic en **Inicio**, señale **Herramientas administrativas** haga clic en **Administración de directivas de grupo**) y, a continuación, complete los siguientes pasos:

1.  En la Administración de directivas de grupo, encuentre el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los equipos de Lync Server se encuentran en un Lync Server con nombre OU, la nueva directiva se debe crear en la OU de Lync Server.

2.  Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en **Crear un GPO en este dominio y vincularlo aquí**.

3.  En el cuadro de diálogo **Nuevo GPO**, escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **Nombre** (por ejemplo, **Audio de Lync Server**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la directiva creada recientemente y, a continuación, haga clic en **Editar**.

Desde aquí el proceso es idéntico con independencia de si está creando una directiva de Active Directory o una directiva local:

1.  En el Editor de administración de directivas de grupo o el Editor de directivas de grupo local, expanda **Configuración del equipo**, expanda **Directivas**, **Configuración de Windows**, haga clic con el botón secundario en **QoS basada en directiva** y, a continuación, haga clic en **Crear nueva directiva**.

2.  En el cuadro de diálogo **QoS basada en directiva**, en la página de apertura, escriba un nombre para la nueva directiva (por ejemplo, **Audio de Lync Server**) en el cuadro **Nombre**. Seleccione **Especificar el valor de DSCP** y establezca el valor en **46**. Deje **Especificar velocidad de salida del acelerador** sin seleccionar y, a continuación, haga clic en **Siguiente**.

3.  En la página siguiente, asegúrese de que la opción **Todas las aplicaciones** está seleccionada y, a continuación, haga clic en **Siguiente**. Esta configuración indica a la red que busque todos los paquetes con un marcado DSCP de 46, no solo paquetes creados por una aplicación específica.

4.  En la tercera página, asegúrese de que tanto la opción **Cualquier dirección IP de origen** como la opción **Cualquier dirección IP de destino** están seleccionadas y, a continuación, haga clic en **Siguiente**. Estos dos valores aseguran que los paquetes se administrarán con independencia de qué equipo (dirección IP) envió dichos paquetes y qué equipo (dirección IP) recibirá dichos paquetes.

5.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**. TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de redes usados más habitualmente por Lync Server y sus aplicaciones cliente.

6.  Debajo del encabezado **Especifique el número de puerto de destino**, seleccione la opción **desde este intervalo o puerto de destino**. En el cuadro de texto que le acompaña, escriba el intervalo de puertos reservado para transmisiones de audio. Por ejemplo, si ha reservado los puertos comprendidos entre 49152 y 57500 para tráfico de audio, especifique el rango de puertos que usan este formato: **49152:57500**. Haga clic en **Finalizar** .

Una vez ha creado la directiva QoS para el tráfico de audio, debería crear una segunda directiva para el tráfico de vídeo. Para crear una directiva para vídeo, siga el mismo procedimiento que ha seguido al crear la directiva de audio, realizando estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Vídeo de Lync Server**).

  - Establezca el valor de DSCP en **34** en lugar de 46. (Tenga en cuenta que no tiene que usar un valor de DSCP de 34. El único requisito es que use un valor de DSCP diferente en lugar del usado para audio.)

  - Use el rango de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 57501 al 65535 para vídeo, establezca el rango de puertos en esto: **57501:65535**. De nuevo, este se debería configurar como el rango de puertos de destino.

Si decide crear una directiva para administrar tráfico de uso compartido de aplicaciones, debe crear una tercera directiva, realizando las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Uso compartido de aplicaciones de Lync Server**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (De nuevo, no tiene que usar un valor de DSCP de 24. El único requisito es que use un valor de DSCP diferente para uso compartido de aplicaciones del que usó para audio o para vídeo.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 40803 al 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos en esto: **40803:49151**.

Las nuevas directivas que ha creado no surtirán efecto hasta que la directiva de grupo se haya actualizado en sus servidores perimetrales. Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde la directiva de grupo se tiene que actualizar:

    Gpudate.exe /force

Este comando se puede ejecutar desde dentro del Lync Server o desde cualquier ventana de comandos que esté ejecutándose bajo las credenciales de administrador. Para ejecutar una ventana de comandos bajo las credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, en **Ejecutar como administrador**. Tenga en cuenta que puede que tenga que reiniciar el servidor perimetral tras ejecutar Gpudate.exe.

Para ayudarse a asegurar que los paquetes de redes se marcan con el valor de DSCP adecuado, también debería crear una nueva entrada de registro en cada equipo completando el siguiente procedimiento:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar** .

2.  En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor de registro, expanda **HKEY\_LOCAL\_MACHINE**, **SYSTEM**, **CurrentControlSet**, **servicios** y, a continuación, **Tcpip**.

4.  Haga clic con el botón secundario en **Tcpip**, seleccione **Nueva** y, a continuación, haga clic en **Clave**. Una vez se haya creado la nueva clave de registro, escriba **QoS** y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, seleccione **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Una vez que se crea el nuevo valor de registro, escriba **No usar NLA** y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Datos de valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor de registro y, a continuación, reinicie el equipo.

