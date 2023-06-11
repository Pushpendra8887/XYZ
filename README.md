<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Register.aspx.cs" Inherits="interview_test.Register" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <table border="3" bgcolor="lime">
                <tr>
                    <td>Name:</td>
                    <td><asp:TextBox ID="txtName" runat="server"></asp:TextBox></td>
                </tr>
                <tr>
                    <td>Age:</td>
                    <td>
                        <asp:TextBox ID="txtAge" textMode="Number" runat="server"></asp:TextBox></td>
                </tr>
                <tr>
                    <td>MobileNo:</td>
                    <td><asp:TextBox ID="txtmobile" TextMode="Number" runat="server"></asp:TextBox></td>
                </tr>
                <tr>
                    <td>Gender:</td>
                    <td>
                        <asp:RadioButton ID="rdbMale" GroupName="gen" runat="server" Text="Male"/>
                        <asp:RadioButton ID="rdbFemale" GroupName="gen" runat="server" Text="Female"/>
                </tr>
                <tr>
                    <td>City:</td>
                    <td>
                        <asp:DropDownList ID="ddlcity" runat="server">
                            <asp:ListItem>--select City--</asp:ListItem>
                            <asp:ListItem>Delhi</asp:ListItem>
                            <asp:ListItem>Noida</asp:ListItem>
                            <asp:ListItem>Banglore</asp:ListItem>
                            <asp:ListItem>Pune</asp:ListItem>
                            <asp:ListItem>Bhopal</asp:ListItem>
                            <asp:ListItem>Jabalpur</asp:ListItem>
                        </asp:DropDownList></td>
                </tr>
                
                <tr>
                    <td colspan="2" align="center" >
                        <asp:Button ID="btnRegister" runat="server" Text="Register" OnClick="btnRegister_Click" /></td>
                </tr>
            </table>
        </div>

        <br />
        <div>
            <asp:GridView ID="gdvShowEmp" runat="server" AutoGenerateColumns="False" BackColor="White" BorderColor="#CCCCCC" BorderStyle="None" BorderWidth="1px" CellPadding="4"  ForeColor="Black" GridLines="Horizontal">
               <Columns>
                   <asp:TemplateField HeaderText="Eid">
                       <ItemTemplate>
                           <asp:Label ID="lblEid" runat="server" Text='<%#Bind("eid") %>'></asp:Label>
                       </ItemTemplate>
                   </asp:TemplateField>

                    <asp:TemplateField HeaderText="Name">
                       <ItemTemplate>
                           <asp:Label ID="lblName" runat="server" Text='<%#Bind("ename") %>'></asp:Label>
                       </ItemTemplate>
                   </asp:TemplateField>


                    <asp:TemplateField HeaderText="Age">
                       <ItemTemplate>
                           <asp:Label ID="lblage" runat="server" Text='<%#Bind("age") %>'></asp:Label>
                       </ItemTemplate>
                   </asp:TemplateField>

                    <asp:TemplateField HeaderText="Gender">
                       <ItemTemplate>
                           <asp:Label ID="lblGender" runat="server" Text='<%#Bind("gender") %>'></asp:Label>
                       </ItemTemplate>
                   </asp:TemplateField>

                   <asp:TemplateField HeaderText="City">
                       <ItemTemplate>
                           <asp:Label ID="lblCity" runat="server" Text='<%#Bind("city") %>'></asp:Label>
                       </ItemTemplate>
                   </asp:TemplateField>
                    <asp:TemplateField HeaderText="Action">
                        <ItemTemplate>
                            <asp:LinkButton ID="lnkEdit" runat="server" Text="Edit" CommandArgument='<%#Bind("eid") %>'  OnCommand="lnkEdit_Command"></asp:LinkButton> ||
                            <asp:LinkButton ID="lnkDelete" runat="server" Text="Delete" CommandArgument='<%#Bind("eid") %>'  OnCommand="lnkDelete_Command" OnClientClick="return confirm('Are you Sure Want to delete(Y/N)?');"></asp:LinkButton>
                        </ItemTemplate>
                    </asp:TemplateField>


               </Columns>

                <FooterStyle BackColor="#CCCC99" ForeColor="Black" />
                <HeaderStyle BackColor="#333333" Font-Bold="True" ForeColor="White" />
                <PagerStyle BackColor="White" ForeColor="Black" HorizontalAlign="Right" />
                <SelectedRowStyle BackColor="#CC3333" Font-Bold="True" ForeColor="White" />
                <SortedAscendingCellStyle BackColor="#F7F7F7" />
                <SortedAscendingHeaderStyle BackColor="#4B4B4B" />
                <SortedDescendingCellStyle BackColor="#E5E5E5" />
                <SortedDescendingHeaderStyle BackColor="#242121" />
            </asp:GridView>
        </div>
    </form>
</body>
</html>
