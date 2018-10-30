---
title: "Definir y configurar un grupo de servidores front-end o un servidor Standard Edition"
TOCTitle: Definir y configurar un grupo de servidores front-end o un servidor Standard Edition
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48275620
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Este procedimiento no requiere pertenencia al grupo de dominio con privilegios o de administrador local. Deberá iniciar sesión en un equipo como usuario estándar.

Si está implementando un servidor Enterprise, se debe ejecutar un número mínimo de Servidores front-end en un grupo en cada momento. En la tabla siguiente, se resumen estos requisitos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end de un grupo</th>
<th>Número de servidores que deben estar en ejecución para que el grupo funcione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 -2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3 -4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5 -6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7 -8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9 -10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11 -12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Para Lync Server 2013, cada vez que agregue o quite un servidor front-end del grupo, debe reiniciar los servicios. La eliminación y la adición de servidores se deben realizar como operaciones independientes. Por ejemplo, si va a agregar dos servidores front-end y a quitar dos servidores front-end, siga este procedimiento: 
> <OL>
> <LI>
> <P>Elimine los dos servidores front-end.</P>
> <LI>
> <P>Publique y reactive a topología.</P>
> <LI>
> <P>Reinicie los servicios</P>
> <LI>
> <P>Añada los dos servidores front-end.</P>
> <LI>
> <P>Publique y reactive a topología.</P>
> <LI>
> <P>Reinicie los servicios.</P></LI></OL>



Una vez definida la topología, siga el siguiente procedimiento para definir un Grupo de servidores front-end para el sitio. Para obtener información detallada sobre cómo definir la topología, consulte [Definir y configurar una topología en Topology Builder para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

## Definición de un Grupo de servidores front-end

1.  En el Asistente para definir un nuevo grupo de servidores front-end, en la página **Definir el nuevo Grupo de servidores front-end**, haga clic en **Siguiente** .

2.  En la página **Definir el FQDN de Grupo de servidores front-end**, escriba un nombre de dominio completo (FQDN) para el grupo de servidores que está creando, haga clic en **Enterprise Edition Grupo de servidores front-end** y luego haga clic en **Siguiente**.

3.  En la página **Definir los equipos de este grupo**, escriba un FQDN de equipo para el primer Servidor front-end del grupo y luego haga clic en **Agregar**. Repita este paso para todos los equipos adicionales (hasta ocho) que desee agregar al grupo de servidores y luego haga clic en **Siguiente**.

4. En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si está implementando solo las características de presencia y mensajería instantánea (MI), deberá activar la casilla **Conferencia** para habilitar la MI de varios participantes, pero no las casillas **Conferencia de acceso telefónico local (RTC)** , **Enterprise Voice** o **Control de admisión de llamadas**, ya que representan características de conferencias de colaboración, voz y vídeo.
    
      - **Conferencia :** esta selección permite un amplio conjunto de características, entre las que se incluyen:
        
          - Mensajería instantánea con más de dos interlocutores en una sesión de mensajería instantánea
        
          - Conferencias, lo que incluye colaboración en documentos, uso compartido de aplicaciones y uso compartido de escritorio
        
          - Conferencia A/V, que habilita a los usuarios para conferencias de audio y vídeo (A/V) en tiempo real sin necesidad de servicios externos como, por ejemplo, el servicio de Live Meeting o un puente de audio de otro fabricante
    
      - **Conferencia de acceso telefónico local (RTC) :** permite a los usuarios unirse a la sección de audio de una conferencia de Lync Server 2013 a través de un teléfono de red telefónica conmutada (RTC) sin necesidad de un proveedor de conferencias de audio.
    
      - **Enterprise Voice :** Enterprise Voice es la solución de Voz sobre IP (VoIP) de Lync Server 2013 que permite a los usuarios realizar y recibir llamadas telefónicas. Debería implementar esta característica si tiene pensado usar Lync Server 2013 para llamadas de voz, correo de voz y otras funciones que usen un dispositivo de hardware o un cliente de software.
    
      - **Sistema de control de admisión de llamadas (CAC) :** el CAC determina, en función del ancho de banda disponible, si permite establecer sesiones de comunicaciones en tiempo real como, por ejemplo, llamadas de voz o de vídeo. Si solo ha implementado mensajería instantánea y presencia, no necesita el CAC, ya que ninguna de estas características lo usa.
    
      - **Servidor de archivado :** el servidor de archivado le ofrece una forma de archivar contenido de MI, contenido de conferencias (reuniones), o ambos que se envían a través del Lync Server 2013.
    
      - **Servidor de supervisión :** el servidor de supervisión le permite recoger datos numéricos que describen la calidad multimedia de su red y sus extremos, la información de uso relacionada con las llamadas VoIP, los mensajes de MI, las conversaciones de A/V, las reuniones, el uso compartido de aplicaciones y la transferencia de archivos, así como la información de errores de llamada y solución de problemas para las llamadas que han fallado.
    

    > [!NOTE]
    > Si desea habilitar el CAC en la implementación, es preciso habilitarlo exactamente en un grupo de servidores por sitio central. El CAC se recomienda si está implementando características de voz o conferencia A/V.

    
    En la tabla siguiente se muestran las características disponibles (arriba) y las funciones que se ofrecen a los usuarios (izquierda). Las selecciones de la tabla son las opciones que debe seleccionar para habilitar dichas características para su organización.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>Conferencia</th>
    <th>Conferencia de acceso telefónico local</th>
    <th>Telefonía IP empresarial</th>
    <th>Control de admisión de llamadas</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Mensajería instantánea y presencia</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="even">
    <td><p>Conferencia</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="odd">
    <td><p>Conferencia A/V</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Telefonía IP empresarial</p></td>
    <td><p></p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  En la página **Seleccionar roles de servidor instalados** , puede instalar el Servidor de mediación en el Servidor front-end o implementarlo como servidor independiente.
    
    Puede instalar el Servidor de mediación en el Grupo de servidores front-end.
    
      - Si desea instalar el Servidor de mediación en el Grupo de servidores front-end de Enterprise Edition, asegúrese de que se han activado las casillas. Los roles de servidor se implementarán en los servidores del grupo.
    
      - Si desea implementar el Servidor de mediación como servidor independiente, desactive la casilla que corresponda. Implementará el Servidor de mediación en un paso de implementación independiente una vez que el Servidor front-end se haya implementado por completo.
    

    > [!NOTE]
    > Se recomienda combinar el servidor de mediación si fuera posible. Para obtener información detallada sobre la compatibilidad con servidores de mediación independientes o combinados, consulte <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Componentes y topologías para el servidor de mediación en Lync Server 2013</A> en la documentación de planeación.



6.  La página **Asociar roles de servidor a este grupo de servidores front-end** le permite definir y asociar roles de servidor al Grupo de servidores front-end. Los tres roles disponibles son:
    
    **Habilitar un Grupo de servidores perimetrales:** define y asocia un único Servidor perimetral o un grupo de servidores perimetrales. Un Servidor perimetral facilita la comunicación y la colaboración entre usuarios de la organización y personas de fuera de la misma, incluidos los usuarios federados.
    
    Existen dos escenarios posibles que pueden usarse para implementar y asociar roles de servidor:
    
    Para el escenario uno, se define una nueva topología para una nueva instalación. Puede acometer la instalación de dos formas:
    
      - Dejar todas las casillas sin activar y proceder con la definición de la topología. Una vez que hayan publicado, configurado y comprobado los roles de servidor front-end y back-end, podrá volver a ejecutar Generador de topologías para agregar los servidores de roles a la topología. Esta estrategia le permitirá comprobar el Grupo de servidores front-end y el servidor basado en SQL Server sin las complicaciones añadidas de los roles adicionales. Una vez completada la prueba inicial, puede volver a ejecutar el Generador de topologías para seleccionar los roles que necesite implementar.
    
      - Seleccione los roles que necesita instalar y, a continuación, configure le hardware para hospedar los roles seleccionados.
    
    Para el escenario dos, tiene una implementación existente y la infraestructura está preparada para nuevos roles, o bien necesita asociar roles existentes con un nuevo Servidor front-end.
    
      - En este caso, seleccionará los roles que pretenda implementar o asociar con el nuevo Servidor front-end. En cualquier caso, continuará con la definición de los roles, la configuración de cualquier hardware necesario y procederá con la instalación.

7.  En la página **Definir el almacén de SQL** , realice una de las operaciones siguientes:
    
      - Para usar el almacén de SQL Server existente que ya se ha definido en la topología, seleccione **Usar un almacén de SQL definido previamente** .
    
      - Para definir una nueva instancia de SQL Server para almacenar la información del grupo de servidores, haga clic en **Nuevo** y, a continuación, especifique **FQDN de SQL Server** en el cuadro de diálogo **Definir un nuevo almacén de SQL** .
    
      - Para especificar el nombre de una instancia de SQL Server, seleccione **Instancia con nombre** y, a continuación, especifique el nombre de la instancia.
    
      - Para usar la instancia predeterminada, haga clic en **Instancia predeterminada** .
    
      - Para utilizar la creación de reflejos de SQL, seleccione **Habilitar creación de reflejos de SQL** y seleccione una instancia existente o cree una nueva instancia.

8.  En la página **Definir el uso compartido de archivos** , siga uno de estos procedimientos:
    
      - Para usar un uso compartido de archivos ya definido en la topología, seleccione **Usar un uso compartido de archivos ya definido** .
    
      - Para definir un nuevo recurso compartido de archivos, seleccione **Definir un nuevo recurso compartido de archivos** , en el cuadro **FQDN de servidor de archivos** , escriba el FQDN del servidor de archivos existente donde se ubicará el recurso compartido de archivos y, a continuación, escriba un nombre para el recurso compartido de archivos en el cuadro **Recurso compartido de archivos** .
    
    > [!IMPORTANT]  
    > El recurso compartido de archivos para Lync Server 2013 no puede ubicarse en el Servidor front-end. Tenga en cuenta que, en este ejemplo, el recurso compartido de archivos se ha colocado en el servidor back-end basado en SQL Server. Esta podría no ser una ubicación óptima para los requisitos de su organización y es posible que un servidor de archivos fuera una opción mejor. Puede definir el uso compartido de archivos sin que este se haya creado. Tendrá que crear el uso compartido de archivos en la ubicación que defina antes de publicar la topología.
    


9.  En la página **Especificar la dirección URL de servicios web** , siga uno o varios de estos procedimientos:
    
    > [!IMPORTANT]  
    > La dirección URL base es la identidad de Servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de Servicios web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
    
    
    > [!WARNING]  
    > Si dispone de más de un Grupo de servidores front-end o de un Servidor front-end, el FQDN de servicios web externos ha de ser único. Por ejemplo, si define el FQDN de servicios web externos de un Servidor front-end como <strong>pool01.contoso.com</strong>, no puede usar <strong>pool01.contoso.com</strong> para otro Grupo de servidores front-end o Servidor front-end.
    
    
    1.  Si está configurando el equilibrio de carga de DNS, active la casilla **Invalidar el FQDN del grupo de servidores de servicios web interno** , escriba la dirección URL base interna (que debe ser diferente al FQDN del grupo de servidores y podría ser, por ejemplo, internal-\<su dirección URL base\>) en **Dirección URL base interna** .
        
        > [!WARNING]  
        > Si decide omitir los servicios web externos con un FQDN autodefinido, todos los FQDN deben ser diferentes de otros Grupo de servidores front-end, Director o un Grupo de directores. <strong>Use solo caracteres estándar</strong> (incluidos A–Z, a–z, 0–9 y guiones) al definir direcciones URL o nombres de dominio completos. No use caracteres Unicode ni de subrayado. Los caracteres no estándar en una URL o FQDN no suelen admitirse en DNS externos y CA públicos (es decir, cuando la URL o FQDN deben asignarse al nombre del sujeto o al nombre alternativo de sujeto en el certificado).
        
    
    2.  Opcionalmente, escriba la dirección URL base externa en **Dirección URL base externa** . Deberá introducir la dirección URL base externa con el fin de diferenciar la asignación de nombres de dominio interna. Por ejemplo, el dominio interno es contoso.net, pero el nombre del dominio externo es contoso.com. La dirección URL se define mediante el nombre de dominio contoso.com. También es importante en el caso de un proxy inverso. El nombre de dominio de la dirección URL base externa será el mismo que el nombre de dominio del FQDN del servidor proxy inverso. La mensajería instantánea y la presencia deben tener acceso HTTP al Grupo de servidores front-end.
    

    > [!NOTE]
    > Para usar el equilibrio de carga de DNS, debe crear los registros DNS correspondientes. Para obtener más información, consulte <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configurar el DNS para el equilibrio de carga en Lync Server 2013</A>.



10. Si seleccionó **Conferencias** en la página **Seleccionar características** , en la página **Seleccionar un servidor de Office Web Apps** seleccione **Asociar el grupo con un servidor de Office Web Apps** y haga clic en **Nuevo** o elija un Servidor Office Web Apps existente de la lista desplegable.

11. En el cuadro de diálogo **Definición de un servidor de Office Web Apps nuevo** , escriba el nombre de dominio completo (FQDN) del equipo de su Servidor Office Web Apps en el cuadro **FQDN del servidor de Office Web Apps** . Cuando lo haga, la dirección URL de descubrimiento de su Servidor Office Web Apps debería aparecer automáticamente en el cuadro **Dirección URL de descubrimiento del servidor de Office Web Apps** .
    
    Si el Servidor Office Web Apps se instaló localmente y en la misma zona de red que Lync Server 2013, la opción **El servidor de Office Web Apps se implementa en una red externa (es decir, perimetral/Internet)** no se debería seleccionar.
    
    Si el Servidor Office Web Apps se implementa fuera de su firewall interno, seleccione la opción **El servidor de Office Web Apps se implementa en una red externa (es decir, perimetral/Internet)** .
    

    > [!NOTE]
    > Para ver información detallada, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuración de la integración de Office Web Apps Server y Lync Server 2013</A>.



12. En la página **Definir el almacén de SQL para el archivado** , seleccione una instancia existente o un servidor SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con los datos de archivado.

13. En la página **Definir el almacén SQL para la supervisión** , seleccione una instancia existente o un servidor SQL Server, o bien defina una nueva instancia para almacenar los datos asociados con los datos de supervisión.

14. Haga clic en **Siguiente**. Si ha definido otros roles de servidor en la página **Asociar roles de servidor con este grupo front-end**, se abrirán páginas de asistente para la configuración de roles independientes para que pueda configurar los roles de servidor.
    
    [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Si no ha seleccionado roles de servidor adicionales para configurarlos e implementarlos, o una vez finalizada la configuración de los roles de servidor adicionales, haga clic en **Finalizar** .

