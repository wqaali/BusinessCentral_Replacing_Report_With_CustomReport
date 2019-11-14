## BusinessCentral_Replacing_Report_With_CustomReport
Business Central is full of Standard Reports But sometime those standard reports does not meet user's requirements, For that a user creates a 
new customized report and wanted to open that in repalcemnt of standard one.

In this small project I have done the same.
This example is not very good as standard but purpose is to show how you can replace standard report with other.
In this example if user click on customer list report then backend programe chanage detect and replaced customer report with purchase invoice

codeunit 50103 "Replace Base Report"
{

    [EventSubscriber(ObjectType::Codeunit, Codeunit::ReportManagement, 'OnAfterSubstituteReport', '', false, false)]
    local procedure OnAfterSubstituteReport(ReportId: Integer; var NewReportId: Integer)
    begin
        if ReportId = Report::"Customer - List"
        then
            NewReportId := Report::"Purchase - Invoice";
    end;
    
}

