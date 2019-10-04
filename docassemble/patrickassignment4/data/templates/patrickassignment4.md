**Memo**


**To:** ${ user.name.first } ${ user.name.last }  

 
**From:** Patrick White  

 
**Date:** ${ format_date(today()) }  

 
You have stated the following information: 
You have told us that 
% if Alberta_resident:
you live in Alberta 
% else:
you do not live in Alberta 
% endif
% if location_matter:
and your legal matter is located in Alberta.
% else:
and your legal matter is in a province other than Alberta.
% endif
% if criminal_matter:
You have told us that this is a Criminal Law matter.
% elif family_matter:
You have told us that this is a Family Law matter.
% else:
This is neither a Family Law matter nor a Criminal Law matter. 
As a result, we will be unable to assist you.
% endif
% if afford_lawyer:
You have told us that you can afford a lawyer.
% else:
You have told us that you cannot afford a lawyer.
% endif
% if has_lawyer:
You have told us that you already have a lawyer
% else:
You do not currently have a lawyer.
% endif
% if acting_lawyer:
 and your lawyer is currently acting for you in this matter.
% endif
% if appeal_matter:
Your matter is an appeal of a matter that you previously received Legal Aid of Alberta assistence.
% endif

% if can_help:
Based on the information that you have provided us today, we have determined that you meet our requirements for assistance. 
A member of our staff will contact you shortly to begin the process. 
% else:
According to what you have told us today, we regretfully must inform you that you do not meet the requirements for assistance at this time.
Thank you, come again.
% endif
 
% if len(household) == 0:
You indicated that you live alone.

% elif len(household) == 1:
You indicated that you live with the following person:

${ household }  

% else:
You indicated that you live with the following people:

${ household } 

% endif

Please print this document, sign it and return it to our office with **9 days** 
(${ format_date( current_datetime() + date_interval(days=9), format='M/d/yyyy' ) }).