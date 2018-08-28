# TBMisSampleDateUSE [TbMis_two]
GO
/****** Object:  Table [dbo].[Bookseller]    Script Date: 2018/8/19 21:44:02 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Bookseller](
	[BooksellerID] [nvarchar](50) NOT NULL,
	[BooksellerNum] [int] IDENTITY(1,1) NOT FOR REPLICATION NOT NULL,
	[BooksellerName] [nvarchar](50) NOT NULL,
	[Contact] [nvarchar](50) NULL,
	[Telephone] [nvarchar](20) NULL,
 CONSTRAINT [pk_Bookseller] PRIMARY KEY NONCLUSTERED 
(
	[BooksellerID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY],
 CONSTRAINT [ak_Bookseller_BooksellerName] UNIQUE NONCLUSTERED 
(
	[BooksellerName] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO
/****** Object:  Table [dbo].[Course]    Script Date: 2018/8/19 21:44:02 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Course](
	[CourseNum] [int] IDENTITY(1,1) NOT NULL,
	[CourseID] [nvarchar](50) NOT NULL,
	[CourseCode] [nvarchar](50) NULL,
	[CourseName] [nvarchar](50) NOT NULL,
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED 
(
	[CourseNum] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO
/****** Object:  Table [dbo].[StudentDeclaration_Bookseller]    Script Date: 2018/8/19 21:44:02 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[StudentDeclaration_Bookseller](
	[DeclarationID] [int] NOT NULL,
	[BooksellerID] [nvarchar](50) NOT NULL,
	[SubscriptionStatus] [nchar](1) NOT NULL,
	[FeedbackDate] [datetime] NULL,
	[FeedbackStaff] [nvarchar](50) NULL,
	[Remark] [nvarchar](200) NULL,
	[ReDeclareStatus] [nchar](1) NOT NULL,
 CONSTRAINT [PK_StudentDeclaration_Bookseller] PRIMARY KEY CLUSTERED 
(
	[DeclarationID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO
/****** Object:  Table [dbo].[StudentWholeData]    Script Date: 2018/8/19 21:44:02 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[StudentWholeData](
	[DeclarationID] [int] IDENTITY(1,1) NOT NULL,
	[TermCode] [nvarchar](20) NOT NULL,
	[TermName] [nvarchar](20) NOT NULL,
	[BatchID] [nvarchar](50) NOT NULL,
	[SchoolID] [nvarchar](50) NOT NULL,
	[SchoolName] [nvarchar](50) NOT NULL,
	[DepartmentID] [nvarchar](50) NOT NULL,
	[DepartmentName] [nvarchar](50) NOT NULL,
	[EducationalType] [nvarchar](50) NULL,
	[TextbookNum2] [int] NULL,
	[ApprovedAmount] [int] NOT NULL,
	[Priority] [nvarchar](50) NOT NULL,
	[Phone] [nvarchar](50) NULL,
	[CheckState] [nvarchar](50) NOT NULL,
	[Remarks] [nvarchar](50) NULL,
	[ClassName] [nvarchar](50) NOT NULL,
	[ClassSize] [nvarchar](50) NOT NULL,
	[DataSign] [nchar](1) NOT NULL,
	[CourseNum] [int] NOT NULL,
 CONSTRAINT [PK_学生用书$] PRIMARY KEY CLUSTERED 
(
	[DeclarationID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO
/****** Object:  Table [dbo].[TeacherDeclaration_Bookseller]    Script Date: 2018/8/19 21:44:02 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[TeacherDeclaration_Bookseller](
	[DeclarationID] [int] NOT NULL,
	[BooksellerID] [nvarchar](50) NOT NULL,
	[SubscriptionStatus] [nchar](1) NOT NULL,
	[FeedbackDate] [datetime] NULL,
	[FeedbackStaff] [nvarchar](50) NULL,
	[Remark] [nvarchar](200) NULL,
	[ReDeclareStatus] [nchar](1) NOT NULL,
 CONSTRAINT [PK_TeacherDeclaration_Bookseller] PRIMARY KEY CLUSTERED 
(
	[DeclarationID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO
/****** Object:  Table [dbo].[TeacherWholeData]    Script Date: 2018/8/19 21:44:02 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[TeacherWholeData](
	[DeclarationID] [int] IDENTITY(1,1) NOT NULL,
	[TermCode] [nvarchar](20) NOT NULL,
	[TermName] [nvarchar](20) NOT NULL,
	[BatchID] [nvarchar](50) NOT NULL,
	[SchoolID] [nvarchar](50) NOT NULL,
	[SchoolName] [nvarchar](50) NOT NULL,
	[DepartmentID] [nvarchar](50) NOT NULL,
	[DepartmentName] [nvarchar](50) NOT NULL,
	[EducationalType] [nvarchar](50) NULL,
	[TextbookNum2] [int] NULL,
	[ApprovedAmount] [int] NOT NULL,
	[Priority] [nvarchar](50) NOT NULL,
	[Phone] [nvarchar](50) NULL,
	[Remarks] [nvarchar](50) NULL,
	[CheckState] [nvarchar](50) NOT NULL,
	[DataSign] [nchar](1) NOT NULL,
	[CourseNum] [int] NOT NULL,
 CONSTRAINT [PK_教师用书$] PRIMARY KEY CLUSTERED 
(
	[DeclarationID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO
/****** Object:  Table [dbo].[Textbook]    Script Date: 2018/8/19 21:44:02 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
SET ANSI_PADDING ON
GO
CREATE TABLE [dbo].[Textbook](
	[TextbookID] [nvarchar](50) NOT NULL,
	[TextbookNum2] [int] IDENTITY(1,1) NOT FOR REPLICATION NOT NULL,
	[TextbookNum]  AS (replicate('0',(8)-len([TextbookNum2]))+CONVERT([nvarchar](10),[TextbookNum2],(0))),
	[Isbn] [nvarchar](20) NOT NULL,
	[TextbookName] [nvarchar](200) NOT NULL,
	[Press] [nvarchar](50) NOT NULL,
	[Author] [nvarchar](50) NOT NULL,
	[Edition] [nvarchar](20) NOT NULL,
	[PrintingCount] [nvarchar](20) NOT NULL,
	[Price] [nvarchar](50) NOT NULL,
	[TextbookType] [nvarchar](50) NULL,
	[Translator] [nvarchar](50) NULL,
	[Language] [nvarchar](20) NULL,
	[Page] [int] NULL,
	[Summary] [nvarchar](200) NULL,
	[Catalog] [nvarchar](200) NULL,
	[IsSelfCompile] [char](1) NOT NULL,
 CONSTRAINT [PK_Textbook] PRIMARY KEY CLUSTERED 
(
	[TextbookNum2] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO
SET ANSI_PADDING OFF
GO
ALTER TABLE [dbo].[Textbook] ADD  CONSTRAINT [DF__Textbook__Textbo__53ED4AC6]  DEFAULT ('?') FOR [TextbookName]
GO
ALTER TABLE [dbo].[Textbook] ADD  CONSTRAINT [ck_Textbook_IsSelfCompile]  DEFAULT ('0') FOR [IsSelfCompile]
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [FK_StudentDeclaration_Bookseller_Bookseller] FOREIGN KEY([BooksellerID])
REFERENCES [dbo].[Bookseller] ([BooksellerID])
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller] CHECK CONSTRAINT [FK_StudentDeclaration_Bookseller_Bookseller]
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [FK_StudentDeclaration_Bookseller_StudentWholeData] FOREIGN KEY([DeclarationID])
REFERENCES [dbo].[StudentWholeData] ([DeclarationID])
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller] CHECK CONSTRAINT [FK_StudentDeclaration_Bookseller_StudentWholeData]
GO
ALTER TABLE [dbo].[StudentWholeData]  WITH CHECK ADD  CONSTRAINT [FK_StudentWholeData_Course] FOREIGN KEY([CourseNum])
REFERENCES [dbo].[Course] ([CourseNum])
GO
ALTER TABLE [dbo].[StudentWholeData] CHECK CONSTRAINT [FK_StudentWholeData_Course]
GO
ALTER TABLE [dbo].[StudentWholeData]  WITH CHECK ADD  CONSTRAINT [FK_StudentWholeData_Textbook] FOREIGN KEY([TextbookNum2])
REFERENCES [dbo].[Textbook] ([TextbookNum2])
GO
ALTER TABLE [dbo].[StudentWholeData] CHECK CONSTRAINT [FK_StudentWholeData_Textbook]
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [FK_TeacherDeclaration_Bookseller_Bookseller] FOREIGN KEY([BooksellerID])
REFERENCES [dbo].[Bookseller] ([BooksellerID])
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller] CHECK CONSTRAINT [FK_TeacherDeclaration_Bookseller_Bookseller]
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [FK_TeacherDeclaration_Bookseller_TeacherWholeData] FOREIGN KEY([DeclarationID])
REFERENCES [dbo].[TeacherWholeData] ([DeclarationID])
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller] CHECK CONSTRAINT [FK_TeacherDeclaration_Bookseller_TeacherWholeData]
GO
ALTER TABLE [dbo].[TeacherWholeData]  WITH CHECK ADD  CONSTRAINT [FK_TeacherWholeData_Course] FOREIGN KEY([CourseNum])
REFERENCES [dbo].[Course] ([CourseNum])
GO
ALTER TABLE [dbo].[TeacherWholeData] CHECK CONSTRAINT [FK_TeacherWholeData_Course]
GO
ALTER TABLE [dbo].[TeacherWholeData]  WITH CHECK ADD  CONSTRAINT [FK_TeacherWholeData_TeacherWholeData] FOREIGN KEY([TextbookNum2])
REFERENCES [dbo].[Textbook] ([TextbookNum2])
GO
ALTER TABLE [dbo].[TeacherWholeData] CHECK CONSTRAINT [FK_TeacherWholeData_TeacherWholeData]
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [CK_StudentDeclaration_Bookseller] CHECK  (([SubscriptionStatus]='3' OR [SubscriptionStatus]='2' OR [SubscriptionStatus]='1' OR [SubscriptionStatus]='0'))
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller] CHECK CONSTRAINT [CK_StudentDeclaration_Bookseller]
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [CK_StudentDeclaration_Bookseller_1] CHECK  (([ReDeclareStatus]='3' OR [ReDeclareStatus]='2' OR [ReDeclareStatus]='1' OR [ReDeclareStatus]='0'))
GO
ALTER TABLE [dbo].[StudentDeclaration_Bookseller] CHECK CONSTRAINT [CK_StudentDeclaration_Bookseller_1]
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [CK_TeacherDeclaration_Bookseller] CHECK  (([SubscriptionStatus]='2' OR [SubscriptionStatus]='1' OR [SubscriptionStatus]='0'))
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller] CHECK CONSTRAINT [CK_TeacherDeclaration_Bookseller]
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller]  WITH CHECK ADD  CONSTRAINT [CK_TeacherDeclaration_Bookseller_1] CHECK  (([ReDeclareStatus]='3' OR [ReDeclareStatus]='2' OR [ReDeclareStatus]='1' OR [ReDeclareStatus]='0'))
GO
ALTER TABLE [dbo].[TeacherDeclaration_Bookseller] CHECK CONSTRAINT [CK_TeacherDeclaration_Bookseller_1]
GO
ALTER TABLE [dbo].[Textbook]  WITH CHECK ADD  CONSTRAINT [ck_IsSelfCompile_Textbook] CHECK  (([IsSelfCompile]='1' OR [IsSelfCompile]='0'))
GO
ALTER TABLE [dbo].[Textbook] CHECK CONSTRAINT [ck_IsSelfCompile_Textbook]
GO
ALTER TABLE [dbo].[Textbook]  WITH CHECK ADD  CONSTRAINT [ck_Page_Textbook] CHECK  (([Page] IS NULL OR [Page]>=(0)))
GO
ALTER TABLE [dbo].[Textbook] CHECK CONSTRAINT [ck_Page_Textbook]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'格式化后的教材编号' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Textbook', @level2type=N'COLUMN',@level2name=N'TextbookNum'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'教材的信息' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Textbook'
GO

