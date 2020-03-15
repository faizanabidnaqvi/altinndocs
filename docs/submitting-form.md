---
title: Submitting form
date: 2020-03-13
slug: submit-form

---
# Basic steps

The RF-1189 form needs to be attached to an existing RF-1030 form. The basic steps to submit a full form are as follows:

1. Find out which RF-1030 form does the user wish to attach the RF-1189 form to. In the app, this will be either the current or the last year.
2. Authenticate the user.
3. Find the ReporteeElementID for the form they wish to attach RF-1189 to.
4. Generate the RF-1189 form
5. Submit a UpdateFormDataBasic request with the correct parameters

# Form to use

Each year, say 2020, requires the form from the previous year to be submitted. But it is possible for users to submit from the year before that too.

For example, in 2020 the application RF-1030 form will be for 2019 (current year submission) and 2018 (previous year)

# Authenticate the user