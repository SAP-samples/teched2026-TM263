# Exercise 4 - Finalize the Tenant Copy
<p align="justify">In this exercise, you will enter the <b>Downtime</b> phase, isolate the source SAP system, and use the <b>RISE with SAP System Transition Workbench</b> to finalize the <b>SAP HANA tenant copy</b>. You will monitor the final replication, review table record count comparisons, and start the application on the Migration Server.</p><br>

## Steps:
Follow these steps to complete the exercise:<br>
1.  In the **SAP HANA Tenant Copy Cockpit**, under **Downtime**, select **Task 1.1 – Finalize Tenant Replication for SAP HANA Tenant Copy**.<br><br>
    ![](images/Screenshot-1-01.png)<br>

2.  In the **Confirm Task Initiation** dialog, choose **Start**.<br>
3.  The workbench starts the **Collect Inputs** phase and retrieves the required system parameters and connection details.<br>
4.  On the **Parameter Summary** page, review the preconfigured values. Leave **Change Parameter Values** unchecked and choose **Next** to continue with the existing configuration.<br><br>
    ![](images/Screenshot-1-02.png)<br>

5.  The workbench starts the **Finalize Replication** phase and displays the required preparation steps. Review the source-isolation checklist, including user logoff, outstanding requests, and background-job considerations, before proceeding.<br>

    > **ℹ️ NOTE**: Isolating the source application server marks the beginning of the **Business Downtime**. From this point onward, users can no longer perform business operations on the source system.

    ![](images/Screenshot-1-03.png)<br>

6.  Open the [Lab Control](https://control.lab.consarea.com/source-isolation/) and log on as **DEMOXXX** (replace *XXX* with your seat number, for example **DEMO001**).<br>
7.  Under **Isolate the Source Application Server**, choose **Stop Application Server**.<br><br>

    > **⚠️ CAUTION**: Before stopping the **Source Application Server**, verify that the displayed hostname matches your assigned **seat number** (for example, **source-001.lab.internal** for seat **001**). **Do not proceed if the hostname does not match!** You could accidentally stop another participant's system. Contact your instructor if you are unsure.

    <br>

    ![](images/Screenshot-1-04.png)<br>

8.  The source application server begins shutting down. Wait while the status changes from **Running** to **Stopping**.<br><br>
    ![](images/Screenshot-1-05.png)<br>

9.  Verify that the source **Application Server** has the status **Stopped**, while **Central Services (ASCS)** remain running. Return to the **System Transition Workbench** and choose **Next** to continue.<br><br>
    ![](images/Screenshot-1-06.png)<br>

10. The workbench prepares to execute **Table Record Checks** to compare record counts between the source and target systems. Leave **Skip table record checks** unchecked and choose **Next** to proceed.<br><br>
    ![](images/Screenshot-1-07.png)<br>

11. Under **Monitor Replication Status**, review the replication information. Verify that the replication status is **ACTIVE** and that the **Backlog Size** has reached `0`, indicating that the outstanding replication data has been transferred.<br><br>
    ![](images/Screenshot-1-08.png)<br>

12. The workbench continues with **SAP HANA tenant replication finalization**, performs the **table record checks**, and starts the application on the **Migration Server**.<br><br>
    ![](images/Screenshot-1-09.png)<br>

13. Review the **Checking Table Records After SAP HANA Replication** results. Verify that the displayed record-count comparisons between the source and target systems have completed successfully.<br><br>
    ![](images/Screenshot-1-10.png)<br>

14. Verify that **Task 1.1 – Finalize Tenant Replication for SAP HANA Tenant Copy** has the status **Completed**, with **100% progress** and all key tasks marked as successful.<br><br>
    ![](images/Screenshot-1-11.png)<br>

15. Choose **Confirm and Continue** to return to the SAP HANA Tenant Copy Cockpit.<br>
16. **Congratulations!** You have successfully finalized the **SAP HANA tenant copy** and completed the replication validation activities.<br><br><br>


## Optional: Test Your Knowledge
Run this optional [quiz](https://quiz-app-per8c91o.cfapps.eu10-005.hana.ondemand.com/tm263-berlin/quiz/zctpe5vp) to test your understanding. If you prefer to skip it, continue with the next exercise.<br>

> **💡 TIP**: To open this link in a new tab, **right-click** and choose **Open Link in New Tab**.
<br>

## Summary
<p align="justify">You have isolated the source application server, finalized <b>SAP HANA tenant replication</b>, and successfully completed the table record count comparisons between the source and target systems.</p>

<p align="justify">The <b>SAP HANA tenant copy</b> is now complete, and the application has been started on the <b>Migration Server</b>. The migration remains in the <b>Downtime</b> phase while the remaining post-processing activities are performed.</p>

Continue to [Exercise 5 - Complete Migration Post-Processing](../ex5/README.md)