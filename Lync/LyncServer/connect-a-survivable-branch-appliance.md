---
title: Conectar una aplicación de sucursal con funciones de supervivencia
TOCTitle: Conectar una aplicación de sucursal con funciones de supervivencia
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49889832
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conectar una aplicación de sucursal con funciones de supervivencia

 

_**Última modificación del tema:** 2012-10-19_

Cada aplicación de sucursal con funciones de supervivencia (SBA) se asocia a un grupo de servidores front-end que sirve como registrador de reserva para SBA. Cuando el grupo de servidores front-end se migra a Lync Server 2013, la SBA debe disociarse del grupo de servidores front-end Lync Server 2010 mientras se actualiza el grupo de servidores. Una vez migrado a Lync Server 2013, la SBA se podrá volver a asociar con el grupo de servidores front-end actualizado. Esta operación implica eliminar la SBA de la topología de Lync Server 2010 heredada en Generador de topologías y, a continuación, agregar la SBA a la topología de Lync Server 2013. Los usuarios hospedados en la SBA de Lync Server 2010 heredada deben trasladarse a otro grupo de servidores antes de eliminar la SBA de la topología. Una vez agregada la SBA a la topología Lync Server 2013, esos usuarios podrán moverse de vuelta a la SBA. A continuación, se resume este procedimiento:

1.  Mover los usuarios de sucursal hospedados en el Lync Server 2010 de SBA heredado a otro grupo de servidores front end.

2.  Quitar la SBA de la topología de Lync Server 2010 heredada para desconectar el grupo de servidores front-end existente como un registrador de reserva.

3.  Agregar la SBA a la topología de Lync Server 2013 y configurar este nuevo grupo de servidores front-end como registrador de reserva.

4.  Mover los usuarios de sucursal a la SBA de Lync Server 2013 nueva.

**Agregar un sitio de sucursal SBA de Lync Server 2010 a la topología**

1.  Abrir **Generador de topologías**.

2.  En el panel de la izquierda, hacer clic con el botón secundario en **Sitios de sucursal** y, a continuación, en **Nuevo sitio de sucursal**.

3.  En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre** y escriba el nombre del sitio de sucursal.

4.  (Opcional) Haga clic en **Descripción** y escriba una descripción significativa para el sitio de sucursal.

5.  Después, haga clic en **Siguiente**.

6.  (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:
    
    1.  Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
    2.  Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
    3.  Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.

7.  Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:
    
    1.  Si utiliza una aplicación o un servidor de sucursal con funciones de supervivencia de Lync 2010 en este sitio, no olvide desactivar la opción **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre el asistente**. Haga clic en **Finalizar**.

8.  Para asociar una SBA de Lync Server 2010 heredada al grupo de servidores front-end Lync Server 2013:
    
    1.  Expanda el sitio de sucursal que ha creado.
    
    2.  Haga clic con el botón derecho en **Lync Server 2010** y, a continuación, en **Nuevo**.
    
    3.  Haga clic en **Aplicación de sucursal con funciones de supervivencia…**

9.  Siga las indicaciones del asistente que se abrirá. Si desea más información sobre los elementos del asistente, consulte [Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    

    > [!NOTE]
    > Solo se puede asociar una aplicación de sucursal con funciones de supervivencia de Lync Server 2010 con un almacén de supervisión de Lync Server 2010.



10. Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.

11. Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

