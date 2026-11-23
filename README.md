# YOURSPAY-HRM
HRM
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>YoursPay HRM — HR Management</title>
  <link rel="stylesheet" href="styles.css" />
  <link rel="stylesheet" href="login.css" />
  <link rel="stylesheet" href="features.css" />
</head>
<body>
  <main class="login-screen" id="loginScreen">
    <section class="login-card" aria-labelledby="loginTitle">
      <a class="brand login-brand" href="#" aria-label="YoursPay HRM"><span class="brand-mark">Y</span><span>YoursPay <span class="brand-light">HRM</span></span></a>
      <div class="login-heading"><p>SECURE WORKSPACE</p><h1 id="loginTitle">Welcome back</h1><span>Sign in to continue to your workspace.</span></div>
      <form id="loginForm" class="login-form">
        <label for="loginRole">Account type</label>
        <select id="loginRole" name="role" required><option value="hr">HR</option><option value="admin">Admin</option><option value="employee">Employee</option></select>
        <label id="loginEmailLabel" for="loginEmail">Work email</label>
        <input id="loginEmail" name="email" type="email" autocomplete="username" placeholder="name@company.com" required />
        <p class="login-email-hint" id="loginEmailHint" hidden>Sign in with the account created by your HR administrator.</p>
        <label for="loginPassword">Password</label>
        <input id="loginPassword" name="password" type="password" autocomplete="current-password" required />
        <label for="apiBaseUrl">HRM API address</label>
        <input id="apiBaseUrl" type="url" placeholder="https://your-api-host/api/v1" autocomplete="url" />
        <p class="login-error" id="loginError" role="alert" hidden>Sign-in failed.</p>
        <button class="button button-primary" type="submit">Sign in securely</button>
      </form>
      <p class="login-disclaimer">Sign-in, employee directory, attendance, and leave requests use the configured HRM API. Payroll and other modules are not yet server-backed. Use HTTPS for the API.</p>
    </section>
  </main>
  <div class="app-shell" id="appShell" hidden>
    <aside class="sidebar" id="sidebar">
      <a class="brand" href="#dashboard" data-page="dashboard" aria-label="YoursPay HRM home"><span class="brand-mark">Y</span><span>YoursPay <span class="brand-light">HRM</span></span></a>
      <div class="workspace-label">WORKSPACE</div>
      <nav class="main-nav" aria-label="Main navigation">
        <a class="nav-link" href="#myLeave" data-page="myLeave" id="myLeaveNavLink" hidden><span class="nav-icon">▤</span>My leave</a>
        <a class="nav-link active" href="#dashboard" data-page="dashboard"><span class="nav-icon">◫</span>Dashboard</a>
        <a class="nav-link" href="#employees" data-page="employees"><span class="nav-icon">♙</span>Employees <span class="nav-count">24</span></a>
        <a class="nav-link" href="#attendance" data-page="attendance"><span class="nav-icon">◷</span>Attendance</a>
        <a class="nav-link" href="#workModel" data-page="workModel"><span class="nav-icon">⌂</span>Work model</a>
        <a class="nav-link" href="#calendar" data-page="calendar"><span class="nav-icon">▦</span>Calendar</a>
        <a class="nav-link" href="#leave" data-page="leave"><span class="nav-icon">▤</span>Leave management <span class="nav-dot"></span></a>
        <a class="nav-link" href="#tasks" data-page="tasks"><span class="nav-icon">☷</span>Tasks</a>
        <a class="nav-link" href="#performance" data-page="performance"><span class="nav-icon">↗</span>Performance</a>
        <a class="nav-link" href="#payroll" data-page="payroll"><span class="nav-icon">₹</span>Payroll</a>
        <a class="nav-link" href="#recruitment" data-page="recruitment"><span class="nav-icon">♙</span>Recruitment & ATS</a>
        <a class="nav-link" href="#learning" data-page="learning"><span class="nav-icon">▣</span>Learning & development</a>
        <a class="nav-link" href="https://yourspay3.oneapp.dev/" target="_blank" rel="noopener noreferrer"><span class="nav-icon">↗</span>Website</a>
        <a class="nav-link" href="https://yourspay4.oneapp.dev/" target="_blank" rel="noopener noreferrer"><span class="nav-icon">↗</span>Appointment Letter</a>
        <div class="workspace-label nav-section-label">MANAGE</div>
        <a class="nav-link" href="#departments" data-page="departments"><span class="nav-icon">▦</span>Departments & roles</a>
        <a class="nav-link" href="#reports" data-page="reports"><span class="nav-icon">▥</span>HR reports</a>
        <a class="nav-link" href="#access" data-page="access"><span class="nav-icon">♧</span>Access & permissions</a>
      </nav>
      <div class="sidebar-bottom">
        <div class="help-card"><div class="help-icon">✦</div><strong>Need a hand?</strong><p>Visit our help center for quick answers.</p><a href="#help" id="supportLink">Get support <span>↗</span></a></div>
        <button class="profile-switcher" type="button" title="Sign out" aria-label="Sign out"><span class="avatar avatar-violet">HR</span><span class="profile-meta"><strong>HR</strong><small>HR Administrator</small></span><span class="switcher-more">Sign out</span></button>
      </div>
    </aside>

    <main class="main-content">
      <header class="topbar">
        <button class="mobile-menu" id="menuToggle" aria-label="Toggle navigation">☰</button>
        <div class="breadcrumb">Workspace <span>/</span> <strong id="breadcrumbPage">Overview</strong></div>
        <div class="topbar-actions"><button class="icon-button" aria-label="Search">⌕</button><button class="icon-button notification-button" aria-label="Notifications">♧<i></i></button><span class="topbar-divider"></span><div class="top-user"><span class="avatar avatar-violet">HR</span><span>HR</span><span class="chevron">⌄</span></div></div>
      </header>

      <div class="page-wrap">
        <section class="page-heading">
          <div><div class="eyebrow" id="todayLabel">MONDAY, OCTOBER 21, 2024</div><h1 id="pageTitle">Good morning, HR <span class="wave">✦</span></h1><p id="pageSubtitle">Here’s what’s happening with your team today.</p></div>
          <div class="heading-actions"><button class="button button-quiet" id="exportButton"><span>⎙</span> Print CRM report</button><a class="button button-quiet" href="https://yourspay4.oneapp.dev/" target="_blank" rel="noopener noreferrer">Appointment Letter</a><button class="button button-primary" id="addEmployee"><span>＋</span> Add employee</button></div>
        </section>


        <section class="content-grid dashboard-only">
          <article class="panel team-pulse-panel">
            <div class="panel-header"><div><h2>Team pulse</h2><p>Collaboration capacity across your team</p></div><span class="pulse-live"><i></i> LIVE</span></div>
            <div class="pulse-body">
              <div class="pulse-score"><div class="pulse-ring" id="teamPulseRing"><div><strong id="teamPulseRate">0%</strong><span>available</span></div></div><div class="pulse-caption"><strong id="teamPulseCount">0 of 0</strong><span>people ready to collaborate</span></div></div>
              <div class="pulse-insights"><div class="pulse-insight"><span class="pulse-insight-icon ready">↗</span><span class="pulse-insight-label">Available now<small>In office or remote</small></span><strong id="teamPulseAvailable">0</strong></div><div class="pulse-insight"><span class="pulse-insight-icon away">◷</span><span class="pulse-insight-label">Away today<small>Leave or unavailable</small></span><strong id="teamPulseAway">0</strong></div></div>
            </div>
            <div class="panel-footer"><span class="live-indicator"></span> Team snapshot updates with attendance <a href="#attendance" data-page="attendance">Open team register <span>→</span></a></div>
          </article>

          <article class="panel leave-panel">
            <div class="panel-header"><div><h2>Leave requests for HR</h2><p>Requests waiting for HR review</p></div><button class="more-button" id="leaveMoreButton" aria-label="Open all leave requests">···</button></div>
            <div class="leave-list" id="dashboardLeaveList"></div>
            <div class="panel-footer"><span><strong id="dashboardPendingLeaveCount">0</strong> pending requests</span><a href="#leave" data-page="leave">Review all <span>→</span></a></div>
          </article>
        </section>

        <section class="panel quick-actions-panel dashboard-only" aria-labelledby="quickActionsTitle">
          <div class="panel-header"><div><h2 id="quickActionsTitle">Quick actions</h2><p>Jump straight into common HR workflows.</p></div></div>
          <div class="quick-actions-list">
            <button class="button button-primary" id="dashboardAddEmployee" type="button"><span>＋</span> Add employee</button>
            <button class="button button-quiet" id="dashboardNewLeave" type="button"><span>▤</span> New leave request</button>
            <a class="button button-quiet" href="#attendance" data-page="attendance"><span>◷</span> Attendance</a>
            <a class="button button-quiet" href="#payroll" data-page="payroll"><span>₹</span> Payroll</a>
            <a class="button button-quiet" href="#calendar" data-page="calendar"><span>▦</span> Team calendar</a>
          </div>
        </section>

        <section class="panel attendance-chart-panel dashboard-only" aria-labelledby="attendanceChartTitle">
          <div class="panel-header"><div><h2 id="attendanceChartTitle">Today’s attendance</h2><p>Team status at a glance · updates with the attendance register</p></div><span class="chart-period">TODAY</span></div>
          <div class="attendance-chart" role="img" aria-label="Attendance status counts for today">
            <div class="chart-column"><span class="chart-value" id="chartPresentValue">0</span><div class="chart-track"><div class="chart-bar chart-present" id="chartPresentBar"></div></div><span class="chart-label">Present</span></div>
            <div class="chart-column"><span class="chart-value" id="chartRemoteValue">0</span><div class="chart-track"><div class="chart-bar chart-remote" id="chartRemoteBar"></div></div><span class="chart-label">Remote</span></div>
            <div class="chart-column"><span class="chart-value" id="chartLeaveValue">0</span><div class="chart-track"><div class="chart-bar chart-leave" id="chartLeaveBar"></div></div><span class="chart-label">On leave</span></div>
            <div class="chart-column"><span class="chart-value" id="chartAbsentValue">0</span><div class="chart-track"><div class="chart-bar chart-absent" id="chartAbsentBar"></div></div><span class="chart-label">Absent</span></div>
          </div>
        </section>
        <section class="panel employees-panel dashboard-only">
          <div class="panel-header employee-heading"><div><h2>Employee directory</h2><p>A snapshot of your growing team</p></div><div class="table-actions"><label class="search-box"><span>⌕</span><input id="employeeSearch" type="search" placeholder="Search employees..." aria-label="Search employees" /></label><select class="filter-button" id="employeeStatusFilter" aria-label="Filter employees by status"><option value="all">All status</option><option value="Active">Active</option><option value="On leave">On leave</option></select></div></div>
          <div class="table-scroll"><table><thead><tr><th>EMPLOYEE</th><th>DEPARTMENT</th><th>ROLE</th><th>STATUS</th><th>JOINED</th><th></th></tr></thead><tbody id="employeeRows"></tbody></table></div>
          <div class="table-bottom"><span>Showing <strong id="visibleCount">4</strong> of <strong id="directoryTotal">4</strong> employees</span><span id="directoryFilterSummary">All employees</span></div>
        </section>
        <section class="panel daily-attendance-panel" id="dailyAttendancePanel" hidden>
          <div class="panel-header attendance-page-header"><div><h2>Daily attendance register</h2><p>Review and update each employee’s status for the selected day.</p></div><label class="attendance-date-label">Attendance date<input id="attendanceDate" type="date" /></label></div>
          <section class="biometric-card" aria-labelledby="biometricTitle">
            <div class="biometric-copy"><h3 id="biometricTitle">Biometric attendance</h3><p id="biometricStatus" aria-live="polite">Set up this device to verify attendance with its biometric authenticator or passkey.</p><small>Local demo only: device verification does not confirm an employee’s identity or securely save records to a company server.</small></div>
            <div class="biometric-actions"><select id="biometricEmployee" class="attendance-status-select" aria-label="Employee for biometric attendance"></select><button class="button button-quiet" id="setupBiometric" type="button">Set up device</button><button class="button button-primary" id="biometricPunch" type="button" disabled>Verify &amp; clock in</button></div>
          </section>
          <div class="attendance-summary" aria-live="polite">
            <div><span class="summary-dot dot-green"></span><span>Present</span><strong id="presentCount">0</strong></div>
            <div><span class="summary-dot dot-blue"></span><span>Working remote</span><strong id="remoteCount">0</strong></div>
            <div><span class="summary-dot dot-orange"></span><span>On leave</span><strong id="leaveCount">0</strong></div>
            <div><span class="summary-dot dot-gray"></span><span>Absent</span><strong id="absentCount">0</strong></div>
          </div>
          <div class="attendance-tools"><label>Timesheet month<input type="month" id="attendanceMonth" /></label><span id="attendanceTimingSummary" aria-live="polite"></span><button class="button button-quiet" id="exportAttendance" type="button">Export timesheet CSV</button></div>
          <div class="table-scroll"><table><thead><tr><th>EMPLOYEE</th><th>DEPARTMENT</th><th>DAILY STATUS</th><th>CHECK IN</th><th>CHECK OUT</th><th>HOURS</th><th>ACTION</th></tr></thead><tbody id="attendanceRows"></tbody></table></div>
          <div class="payroll-note">Attendance records are saved to the connected HRM API and refreshed automatically.</div>
        </section>
        <section class="panel leave-management-panel" id="leaveManagementPanel" hidden>
          <div class="panel-header"><div><h2>Leave requests for HR Manager</h2><p>Review pending requests and record decisions in the connected HRM API.</p></div><div class="workflow-actions"><button class="button button-quiet" id="exportLeaveCsv" type="button">Export CSV</button><button class="button button-primary" id="newLeaveRequest">＋ New request</button></div></div>
          <div class="leave-list leave-management-list" id="leaveManagementList"></div>
          <div class="payroll-note">Requests and review decisions sync through the API. Leave balances and policy calculations are not included.</div>
        </section>
        <section class="panel employee-leave-panel" id="employeeLeavePanel" hidden>
          <div class="panel-header employee-leave-header"><div><h2>My monthly leave</h2><p>Submit time off and follow HR decisions for your requests.</p></div><div class="employee-leave-actions"><label>Month<input type="month" id="employeeLeaveMonth" /></label><button class="button button-primary" id="employeeNewLeave" type="button">＋ Request leave</button></div></div>
          <div class="employee-leave-summary" aria-live="polite">
            <div><span>Requests this month</span><strong id="employeeMonthRequests">0</strong></div>
            <div><span>Pending</span><strong id="employeeMonthPending">0</strong></div>
            <div><span>Approved</span><strong id="employeeMonthApproved">0</strong></div>
            <div><span>Estimated CL balance</span><strong id="employeeClBalance">12</strong></div>
            <div><span>Estimated PL balance</span><strong id="employeePlBalance">20</strong></div>
          </div>
          <section class="employee-self-service" aria-label="Employee self-service">
            <div><h3>My profile</h3><p id="employeeSelfProfile">Sign in as an employee to view your details.</p><button class="button button-quiet" id="editSelfProfile" type="button">Update contact details</button></div>
            <div><h3>My salary slips</h3><div id="employeePayslips" class="self-service-list"></div></div>
            <div><h3>Bank details</h3><p id="employeeBankDetails">Add or update your bank details in My profile.</p><button class="button button-quiet" id="editSelfBank" type="button">Update bank details</button></div>
            <div><h3>Expense claims</h3><form id="expenseClaimForm" class="self-service-form"><label>Claim description<input name="description" maxlength="120" required /></label><label>Amount (INR)<input name="amount" type="number" min="0.01" step="0.01" required /></label><button class="button button-quiet" type="submit">＋ Submit claim</button></form><div id="employeeExpenseClaims" class="self-service-list"></div></div>
            <div><h3>Company policies</h3><div class="self-service-list policy-list"><p>Leave policy <span>Review with HR</span></p><p>Code of conduct <span>Contact HR for current copy</span></p><p>Expense policy <span>Confirm eligible expenses with HR</span></p></div></div>
            <div><h3>Tamil Nadu government holidays</h3><div id="employeeHolidays" class="self-service-list"></div></div>
          </section>
          <div class="payroll-note">Bank details, profile updates, and expense claims are stored only in this browser demo. Do not enter real banking information or sensitive financial data.</div>
          <div class="leave-list leave-management-list" id="employeeLeaveList"></div>
          <div class="payroll-note">Leave balances are illustrative estimates assuming 12 CL and 20 PL annually; confirm your employer’s policy. Monthly totals reflect approved working days, excluding weekends and listed recurring public holidays.</div>
        </section>
        <section class="panel payroll-panel" id="payrollPanel" hidden>
          <div class="panel-header"><div><h2>Salary & payroll records</h2><p>Save salary slips locally and print individual slips or the full report · INR ₹</p></div><div class="payroll-header-actions"><span class="payroll-total">Saved salary slips<strong id="salarySlipCount">0</strong></span><a class="button button-quiet" href="https://yourspay2.oneapp.dev/" target="_blank" rel="noopener noreferrer">Open YoursPay</a><button class="button button-quiet" id="exportPayrollCsv" type="button">Export CSV</button><button class="button button-quiet" id="printPayrollReport" type="button">Print report</button><button class="button button-primary" id="addSalarySlip" type="button">＋ Add salary slip</button></div></div>
          <div class="table-scroll"><table><thead><tr><th>EMPLOYEE</th><th>PAY PERIOD</th><th>BASIC (INR)</th><th>ALLOWANCES</th><th>DEDUCTIONS</th><th>NET PAY</th><th>STATUS</th><th>ACTIONS</th></tr></thead><tbody id="salarySlipRows"></tbody></table></div>
          <div class="payroll-note">Salary slips are stored in this browser only. This local demo is not a secure payroll system or company-wide database.</div>
        </section>
        <section class="panel work-model-panel" id="workModelPanel" hidden>
          <div class="panel-header"><div><h2>Team work model</h2><p>Set each employee’s regular work arrangement and keep your team roster up to date.</p></div><button class="button button-quiet" id="exportWorkModelCsv" type="button">Export CSV</button></div>
          <div class="work-model-summary" aria-live="polite">
            <div><span>On-site</span><strong id="onsiteCount">0</strong></div>
            <div><span>Hybrid</span><strong id="hybridCount">0</strong></div>
          </div>
          <div class="table-scroll"><table><thead><tr><th>EMPLOYEE</th><th>DEPARTMENT</th><th>ROLE</th><th>WORK ARRANGEMENT</th></tr></thead><tbody id="workModelRows"></tbody></table></div>
          <div class="payroll-note">Work arrangements are stored in this browser only. Confirm company policy and any local employment requirements before using these settings.</div>
        </section>
        <section class="panel tasks-panel" id="tasksPanel" hidden>
          <div class="panel-header"><div><h2>Department work board</h2><p>Create, assign, and track operational work by department.</p></div><button class="button button-primary" id="addTaskButton" type="button">＋ Create task</button></div>
          <div class="workflow-summary" aria-live="polite">
            <div><span>Open</span><strong id="openTaskCount">0</strong></div>
            <div><span>In progress</span><strong id="inProgressTaskCount">0</strong></div>
            <div><span>Completed</span><strong id="completedTaskCount">0</strong></div>
          </div>  
          <div class="table-scroll"><table><thead><tr><th>TASK</th><th>DEPARTMENT</th><th>ASSIGNED TO</th><th>DUE DATE</th><th>PRIORITY</th><th>STATUS</th></tr></thead><tbody id="taskRows"></tbody></table></div>
          <div class="payroll-note">Workflow changes save in this browser and sync to other open tabs on this device. Shared live access across users requires a connected server.</div>
        </section>
        <section class="panel performance-panel" id="performancePanel" hidden>
          <div class="panel-header"><div><h2>Performance goals &amp; check-ins</h2><p>Set clear objectives, track progress, and record manager feedback.</p></div><div class="workflow-actions"><button class="button button-quiet" id="exportGoalsCsv" type="button">Export CSV</button><button class="button button-primary" id="addGoalButton" type="button">＋ Add goal</button></div></div>
          <div class="workflow-summary" aria-live="polite">
            <div><span>Not started</span><strong id="goalNotStartedCount">0</strong></div>
            <div><span>In progress</span><strong id="goalInProgressCount">0</strong></div>
            <div><span>Completed</span><strong id="goalCompletedCount">0</strong></div>
          </div>
          <div class="table-scroll"><table><thead><tr><th>EMPLOYEE</th><th>GOAL / OBJECTIVE</th><th>TARGET DATE</th><th>PROGRESS</th><th>MANAGER CHECK-IN</th><th>ACTION</th></tr></thead><tbody id="performanceRows"></tbody></table></div>
          <div class="payroll-note">Goals and check-in notes are saved in this browser only. Use regular conversations alongside these records; they are not a formal appraisal system.</div>
        </section>
        <section class="panel recruitment-panel" id="recruitmentPanel" hidden>
          <div class="panel-header"><div><h2>Recruitment &amp; applicant tracking</h2><p>Manage local job postings, candidate stages, and your searchable talent pool.</p></div><div class="workflow-actions"><button class="button button-quiet" id="addApplicantButton" type="button">＋ Add candidate</button><button class="button button-primary" id="addJobButton" type="button">＋ Post a role</button></div></div>
          <div class="workflow-summary"><div><span>Open roles</span><strong id="openJobCount">0</strong></div><div><span>Applicants</span><strong id="applicantCount">0</strong></div><div><span>Offers</span><strong id="offerCount">0</strong></div></div>
          <h3 class="module-subheading">Job postings</h3><div id="jobPostingList" class="job-posting-list"></div>
          <div class="panel-header talent-pool-header"><div><h2>Candidate pipeline &amp; talent pool</h2><p>Search past applicants and move candidates through your hiring stages.</p></div><label class="search-box"><span>⌕</span><input id="candidateSearch" type="search" placeholder="Search candidates..." aria-label="Search talent pool" /></label></div>
          <div class="table-scroll"><table><thead><tr><th>CANDIDATE</th><th>ROLE</th><th>EMAIL</th><th>STAGE</th><th>ADDED</th></tr></thead><tbody id="candidateRows"></tbody></table></div>
          <div class="payroll-note">Job postings and applicants are saved locally in this browser. Publishing to external job boards or a public careers page requires a connected service.</div>
        </section>
        <section class="panel learning-panel" id="learningPanel" hidden>
          <div class="panel-header"><div><h2>Learning &amp; development</h2><p>Assign training, track skill development, and monitor certification renewals.</p></div><button class="button button-primary" id="addTrainingButton" type="button">＋ Assign training</button></div>
          <div class="workflow-summary"><div><span>Not started</span><strong id="trainingNotStarted">0</strong></div><div><span>In progress</span><strong id="trainingInProgress">0</strong></div><div><span>Completed</span><strong id="trainingCompleted">0</strong></div></div>
          <div class="table-scroll"><table><thead><tr><th>EMPLOYEE</th><th>COURSE / CERTIFICATION</th><th>TYPE</th><th>DUE / RENEWAL</th><th>STATUS</th><th>ACTION</th></tr></thead><tbody id="trainingRows"></tbody></table></div>
          <div class="payroll-note">Training assignments and renewal dates are local reminders, not evidence of certification or course completion.</div>
        </section>
        <section class="panel departments-panel" id="departmentsPanel" hidden>
          <div class="panel-header"><div><h2>Departments in your directory</h2><p>Departments and roles are automatically grouped from saved employee records.</p></div><div class="department-header-actions"><span class="report-period"><strong id="departmentCount">0</strong> departments</span><button class="button button-primary" id="departmentsAddEmployee" type="button">＋ Add employee</button></div></div>
          <div class="table-scroll"><table><thead><tr><th>DEPARTMENT</th><th>EMPLOYEES</th><th>ROLES IN THIS DEPARTMENT</th><th>ACTIONS</th></tr></thead><tbody id="departmentRows"></tbody></table></div>
          <div class="payroll-note">Department and role lists reflect the current employee directory and are saved with employee records in this browser.</div>
        </section>
        <section class="panel calendar-panel" id="calendarPanel" hidden>
          <div class="panel-header"><div><h2>Government holidays</h2><p>Tamil Nadu public holidays.</p></div></div>
          <div class="calendar-toolbar"><button class="calendar-nav" id="previousMonth" aria-label="Previous month">←</button><strong id="calendarMonth"></strong><button class="calendar-nav" id="nextMonth" aria-label="Next month">→</button></div>
          <div class="calendar-legend" aria-label="Calendar legend"><span><i class="holiday-key"></i> Tamil Nadu public holiday</span></div>
          <div class="calendar-grid" id="calendarGrid" aria-label="Calendar dates"></div>
          <div class="calendar-selection" id="calendarSelection" aria-live="polite">Select a date to check for a government holiday.</div>
          <div class="payroll-note">Holiday markers show recurring dates only. Check the current Tamil Nadu government notification for the complete official list and variable-date holidays.</div>
        </section>
        <section class="panel leave-report-panel" id="leaveReportPanel" hidden>
          <div class="panel-header"><div><h2>CL &amp; PL leave report</h2><p>Casual Leave (CL) and Privilege Leave (PL) summary for HR Manager review</p></div><span class="report-period">Illustrative annual balances</span></div>
          <div class="table-scroll"><table><thead><tr><th>EMPLOYEE</th><th>DEPARTMENT</th><th>CL USED</th><th>CL BALANCE</th><th>PL USED</th><th>PL BALANCE</th></tr></thead><tbody><tr><td colspan="6" class="empty-state">Leave usage figures have not been provided for the current directory.</td></tr></tbody></table></div>
          <div class="payroll-note">Leave balances are not inferred from the employee directory. Confirm your company’s CL/PL policy and records before using this report.</div>
        </section>
        <section class="panel module-notice" id="moduleNotice" hidden aria-live="polite"><div class="panel-header"><div><h2 id="moduleNoticeTitle"></h2><p id="moduleNoticeText"></p></div></div><div class="module-notice-links"><a href="#employees" data-page="employees">Employee directory</a><a href="#attendance" data-page="attendance">Daily attendance</a><a href="#leave" data-page="leave">Leave requests</a><a href="#reports" data-page="reports">CL &amp; PL report</a></div><p class="payroll-note">This browser-based demo saves supported changes locally on this device. It does not provide shared accounts, secure payroll processing, or a company-wide database.</p></section>
        <footer class="page-footer dashboard-only">© 2024 YoursPay HRM <span>•</span> Built for people, powered by care.</footer>
      </div>
    </main>
  </div>
  <dialog class="employee-dialog" id="employeeDialog" aria-labelledby="employeeDialogTitle">
    <form id="employeeForm" class="employee-form">
      <div class="dialog-heading"><div><h2 id="employeeDialogTitle">Add employee</h2><p>Enter the employee’s details below.</p></div><button class="dialog-close" id="closeEmployeeDialog" type="button" aria-label="Close form">×</button></div>
      <div class="form-grid">
        <label>Full name<input name="name" type="text" autocomplete="name" required /></label>
        <label>Email address<input name="email" type="email" autocomplete="email" /></label>
        <label>Department<input name="department" type="text" list="departmentRoleOptions" required /></label>
        <label>Role<input name="role" type="text" list="departmentRoleOptions" required /></label>
        <datalist id="departmentRoleOptions">
          <option value="Operation Head"></option>
          <option value="HR Manager"></option>
          <option value="Credit Officer"></option>
          <option value="Relationship officer"></option>
          <option value="Operational Associate"></option>
          <option value="Branch Manager"></option>
          <option value="Assistant Branch Manager"></option>
          <option value="Team Leader"></option>
          <option value="Tele Caller"></option>
          <option value="Teller"></option>
          <option value="Cashier"></option>
          <option value="Customer Support"></option>
          <option value="Front Office"></option>
          <option value="HR Executive"></option>
          <option value="Sales Manager"></option>
          <option value="Sales Executive"></option>
          <option value="Sales Officer"></option>
          <option value="Collection Executive"></option>
          <option value="Accountant"></option>
          <option value="Office Assistant"></option>
          <option value="Gold Appraiser"></option>
          <option value="Sales Head"></option>
        </datalist>
        <label>Status<select name="status"><option>Active</option><option>On leave</option></select></label>
        <label>Joined date<input name="joined" type="date" /></label>
        <label>Phone<input name="phone" type="tel" autocomplete="tel" /></label>
        <label>Bank account holder<input name="bankAccountName" type="text" autocomplete="cc-name" /></label>
        <label>Bank account number<input name="bankAccountNumber" type="text" inputmode="numeric" autocomplete="off" /></label>
        <label>IFSC code<input name="bankIfsc" type="text" autocomplete="off" /></label>
        <label>Bank name<input name="bankName" type="text" /></label>
        <label>Emergency contact<input name="emergencyName" type="text" /></label>
        <label>Emergency phone<input name="emergencyPhone" type="tel" /></label>
        <label>Document link<input name="documentLink" type="url" placeholder="https://…" /></label>
        <label class="form-wide">Address<textarea name="address" rows="2"></textarea></label>
        <label class="form-wide">Job history / notes<textarea name="jobHistory" rows="3" placeholder="Role changes, dates, and notes"></textarea></label>
      </div>
      <div class="dialog-actions"><button class="button button-quiet" id="cancelEmployeeForm" type="button">Cancel</button><button class="button button-primary" type="submit">Save employee</button></div>
    </form>
  </dialog>
  <dialog class="employee-dialog" id="taskDialog" aria-labelledby="taskDialogTitle">
    <form id="taskForm" class="employee-form">
      <div class="dialog-heading"><div><h2 id="taskDialogTitle">Create operational task</h2><p>Assign work to a department and track its progress.</p></div><button class="dialog-close" id="closeTaskDialog" type="button" aria-label="Close form">×</button></div>
      <div class="form-grid">
        <label class="form-wide">Task title<input name="title" type="text" maxlength="120" required /></label>
        <label>Department<select name="department" id="taskDepartment" required></select></label>
        <label>Assigned employee<select name="assignee" id="taskAssignee" required></select></label>
        <label>Due date<input name="dueDate" type="date" required /></label>
        <label>Priority<select name="priority"><option>Normal</option><option>High</option><option>Urgent</option><option>Low</option></select></label>
        <label>Status<select name="status"><option>Open</option><option>In progress</option><option>Completed</option></select></label>
        <label class="form-wide">Work details<input name="details" type="text" maxlength="240" placeholder="Optional instructions or context" /></label>
      </div>
      <div class="dialog-actions"><button class="button button-quiet" id="cancelTaskForm" type="button">Cancel</button><button class="button button-primary" type="submit">Save task</button></div>
    </form>
  </dialog>
  <dialog class="employee-dialog" id="performanceGoalDialog" aria-labelledby="performanceGoalDialogTitle">
    <form id="performanceGoalForm" class="employee-form">
      <div class="dialog-heading"><div><h2 id="performanceGoalDialogTitle">Add performance goal</h2><p>Agree on a measurable objective and the next check-in.</p></div><button class="dialog-close" id="closePerformanceGoalDialog" type="button" aria-label="Close form">×</button></div>
      <div class="form-grid">
        <label>Employee<select name="employeeEmail" id="performanceEmployee" required></select></label>
        <label>Target date<input name="targetDate" type="date" required /></label>
        <label class="form-wide">Goal / objective<input name="goal" type="text" maxlength="160" placeholder="e.g. Complete the onboarding playbook" required /></label>
        <label>Progress<select name="status"><option>Not started</option><option>In progress</option><option>Completed</option></select></label>
        <label class="form-wide">Manager check-in notes<input name="notes" type="text" maxlength="240" placeholder="Optional feedback or next step" /></label>
      </div>
      <div class="dialog-actions"><button class="button button-quiet" id="cancelPerformanceGoalForm" type="button">Cancel</button><button class="button button-primary" type="submit">Save goal</button></div>
    </form>
  </dialog>
  <dialog class="employee-dialog" id="salarySlipDialog" aria-labelledby="salarySlipDialogTitle">
    <form id="salarySlipForm" class="employee-form">
      <div class="dialog-heading"><div><h2 id="salarySlipDialogTitle">Add salary slip</h2><p>Record employee pay details for the selected month.</p></div><button class="dialog-close" id="closeSalarySlipDialog" type="button" aria-label="Close form">×</button></div>
      <div class="form-grid">
        <label>Employee<select name="employeeEmail" id="salarySlipEmployee" required></select></label>
        <label>Pay period<input name="period" type="month" required /></label>
        <label>Basic salary (INR)<input name="basic" type="number" min="0" step="0.01" required /></label>
        <label>Allowances (INR)<input name="allowances" type="number" min="0" step="0.01" value="0" required /></label>
        <label>Deductions (INR)<input name="deductions" type="number" min="0" step="0.01" value="0" required /></label>
        <label>Payment status<select name="status"><option>Pending</option><option>Paid</option></select></label>
      </div>
      <div class="dialog-actions"><button class="button button-quiet" id="cancelSalarySlipForm" type="button">Cancel</button><button class="button button-primary" type="submit">Save salary slip</button></div>
    </form>
  </dialog>
  <dialog class="employee-dialog" id="employeeProfileDialog" aria-labelledby="employeeProfileTitle">
    <div class="employee-form">
      <div class="dialog-heading"><div><h2 id="employeeProfileTitle">Employee profile</h2><p id="employeeProfileSummary"></p></div><button class="dialog-close" id="closeEmployeeProfile" type="button" aria-label="Close profile">×</button></div>
      <div id="employeeProfileDetails" class="profile-details"></div>
      <section class="profile-documents" aria-labelledby="profileDocumentsTitle">
        <div class="profile-documents-heading"><div><h3 id="profileDocumentsTitle">Employee documents</h3><p>Files are stored in this browser only; do not upload highly sensitive records.</p></div><div class="profile-document-upload"><input id="employeeDocumentInput" type="file" accept=".pdf,.doc,.docx,.jpg,.jpeg,.png,.txt" hidden /><button class="button button-quiet profile-upload-button" id="chooseEmployeeDocument" type="button">＋ Choose file</button><span class="profile-selected-file" id="selectedEmployeeDocument" aria-live="polite">No file selected</span><button class="button button-primary" id="storeEmployeeDocument" type="button" disabled>Store document</button></div></div>
        <div id="employeeDocumentList" class="profile-document-list" aria-live="polite"><p class="profile-history-empty">Loading documents…</p></div>
      </section>
      <div class="dialog-actions"><button class="button button-quiet" id="profileEditButton" type="button">Edit profile</button><button class="button button-primary" id="closeEmployeeProfileDone" type="button">Done</button></div>
    </div>
  </dialog>
  <dialog class="employee-dialog" id="jobDialog" aria-labelledby="jobDialogTitle"><form id="jobForm" class="employee-form"><div class="dialog-heading"><div><h2 id="jobDialogTitle">Post a role</h2><p>Create a local job posting for your hiring pipeline.</p></div><button class="dialog-close" id="closeJobDialog" type="button" aria-label="Close form">×</button></div><div class="form-grid"><label class="form-wide">Job title<input name="title" maxlength="120" required /></label><label>Department<input name="department" maxlength="80" required /></label><label>Location<input name="location" maxlength="80" placeholder="On-site / Hybrid / Remote" required /></label><label class="form-wide">Job summary<textarea name="summary" rows="3" maxlength="400" required></textarea></label></div><div class="dialog-actions"><button class="button button-quiet" id="cancelJobForm" type="button">Cancel</button><button class="button button-primary" type="submit">Save job posting</button></div></form></dialog>
  <dialog class="employee-dialog" id="applicantDialog" aria-labelledby="applicantDialogTitle"><form id="applicantForm" class="employee-form"><div class="dialog-heading"><div><h2 id="applicantDialogTitle">Add candidate</h2><p>Add an applicant to the talent pool and candidate pipeline.</p></div><button class="dialog-close" id="closeApplicantDialog" type="button" aria-label="Close form">×</button></div><div class="form-grid"><label>Candidate name<input name="name" maxlength="100" required /></label><label>Email<input name="email" type="email" required /></label><label>Role<select name="jobId" id="applicantJob" required></select></label><label>Stage<select name="stage"><option>Screening</option><option>Interview</option><option>Assessment</option><option>Offer</option><option>Hired</option><option>Talent pool</option><option>Rejected</option></select></label></div><div class="dialog-actions"><button class="button button-quiet" id="cancelApplicantForm" type="button">Cancel</button><button class="button button-primary" type="submit">Save candidate</button></div></form></dialog>
  <dialog class="employee-dialog" id="trainingDialog" aria-labelledby="trainingDialogTitle"><form id="trainingForm" class="employee-form"><div class="dialog-heading"><div><h2 id="trainingDialogTitle">Assign training</h2><p>Track a course or certification and its renewal date.</p></div><button class="dialog-close" id="closeTrainingDialog" type="button" aria-label="Close form">×</button></div><div class="form-grid"><label>Employee<select name="employeeEmail" id="trainingEmployee" required></select></label><label>Type<select name="type"><option>Training course</option><option>Certification</option></select></label><label class="form-wide">Course / certification<input name="title" maxlength="140" required /></label><label>Due / renewal date<input name="dueDate" type="date" required /></label><label>Status<select name="status"><option>Not started</option><option>In progress</option><option>Completed</option></select></label></div><div class="dialog-actions"><button class="button button-quiet" id="cancelTrainingForm" type="button">Cancel</button><button class="button button-primary" type="submit">Save assignment</button></div></form></dialog>
  <div id="salarySlipPrintView" class="salary-slip-print" aria-live="polite"></div>
  <dialog class="employee-dialog" id="leaveDialog" aria-labelledby="leaveDialogTitle">
    <form id="leaveForm" class="employee-form">
      <div class="dialog-heading"><div><h2 id="leaveDialogTitle">New leave request</h2><p>Record a request for HR Manager review.</p></div><button class="dialog-close" id="closeLeaveDialog" type="button" aria-label="Close form">×</button></div>
      <div class="form-grid">
        <label>Employee name<input name="name" type="text" required /></label>
        <label>Leave type<select name="type"><option>Casual Leave (CL)</option><option>Privilege Leave (PL)</option><option>Sick Leave</option><option>Other</option></select></label>
        <label>Start date<input name="start" type="date" required /></label>
        <label>End date<input name="end" type="date" required /></label>
        <label class="form-wide">Reason<input name="reason" type="text" maxlength="160" required /></label>
      </div>
      <div class="dialog-actions"><button class="button button-quiet" id="cancelLeaveForm" type="button">Cancel</button><button class="button button-primary" type="submit">Submit request</button></div>
    </form>
  </dialog>
  <div class="toast" id="toast" role="status"></div>
  <script src="script.js"></script>
  <script src="api-client.js"></script>
</body>
</html>
